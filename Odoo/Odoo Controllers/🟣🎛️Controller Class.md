For creating a web controller, initially, we need to create a directory called “Controllers” with `__init__.py` and a python file inside our custom module.
```
from odoo import http, _
from odoo.http import request
class ResPartnerController(http.Controller):
	@http.route('/contacts', type='http', auth='public', website=True)
	def contact_details(self, **kwargs):
    	partner_data = request.env['res.partner'].sudo().search([])
    	values = {
        	'partners': partner_data,
    	}
    	return request.render("library_management.contact_details_template", values)
```
- Decorating with route() is necessary to keep the method (and route) visible: if the method is redefined without decorating, it will be “unpublished”
- The Controllers in Odoo are actually inherited from the “Controller” class, as you can see from the above code. The `@http.route()` defined in the controller specifies some details like the `url` of the page that need to be redirected, the type of the request (can be `http` or `json`), `auth` for specifying who can access the `url`, website parameter for specifying the controller is linked with a page (it will take either True or False values).
[[🟣🎛️HTTP route]]