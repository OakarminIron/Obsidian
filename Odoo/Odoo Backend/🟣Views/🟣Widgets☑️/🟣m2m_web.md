```xml
<?xml version="1.0" encoding="utf-8"?>  
<odoo>  
   <template id="many2many_odoo_blog"  
             inherit_id="portal.portal_my_details_fields">  
       <xpath expr="//input[@name='vat']/.." position="after">  
           <lable>Tags</lable>  
           <select class="js-example-basic-multiple col-xl-6 mb-1 new-get_data"  
                   multiple="multiple">  
               <t t-foreach="tags" t-as="tag">  
                   <option t-att-value="tag" t-esc="tag.name"/>  
               </t>  
           </select>  
       </xpath>  
   </template>  
</odoo>
```

```Javascript
/** @odoo-module */
import publicWidget from "@web/legacy/js/public/public_widget";
console.log(publicWidget,"publicWidget")
var CustomForm = publicWidget.Widget.extend({
    selector: '.new-get_data',
    start: function () {
    $('.js-example-basic-multiple').select2();
    }
    });
publicWidget.registry.Many2many_tag = CustomForm;
return CustomForm;
```

```Python
from odoo.addons.portal.controllers.portal import CustomerPortal
from odoo.http import request, route
class CustomerPortal(CustomerPortal):
   @route()
   def account(self, redirect=None, **post):
       res = super(CustomerPortal, self).account(self, **post)
       values = self._prepare_portal_layout_values()
       partner = request.env.user.partner_id
       values.update({
           'error': {},
           'error_message': [],
       })
       if post and request.httprequest.method == 'POST':
           error, error_message = self.details_form_validate(post)
           values.update({'error': error, 'error_message': error_message})
           values.update(post)
           if not error:
               values = {key: post[key] for key in
                         self._get_mandatory_fields()}
               values.update(
                   {key: post[key] for key in self._get_optional_fields() if
                    key in post})
               for field in set(['country_id', 'state_id']) & set(
                       values.keys()):
                   try:
                       values[field] = int(values[field])
                   except:
                       values[field] = False
               values.update({'zip': values.pop('zipcode', '')})
               self.on_account_update(values, partner)
               partner.sudo().write(values)
               if redirect:
                   return request.redirect(redirect)
               return request.redirect('/my/home')
       countries = request.env['res.country'].sudo().search([])
       states = request.env['res.country.state'].sudo().search([])
       tags = request.env['crm.tag'].sudo().search([])
       values.update({
           'partner': partner,
           'countries': countries,
           'states': states,
           'tags': tags,
           'has_check_vat': hasattr(request.env['res.partner'], 'check_vat'),
           'partner_can_edit_vat': partner.can_edit_vat(),
           'redirect': redirect,
           'page_name': 'my_details',
       })
       response = request.render("portal.portal_my_details", values)
       response.headers['X-Frame-Options'] = 'SAMEORIGIN'
       response.headers['Content-Security-Policy'] = "frame-ancestors 'self'"
       return response
       return res
```

[Cybrosys](https://www.cybrosys.com/blog/how-to-add-many2many-fields-in-odoo17-website-form)

