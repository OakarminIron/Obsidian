```xml
<record id="crm_dashboard_action"      model="ir.actions.client">  
   <field name="name">CRM Dashboard</field>  
   <field name="tag">crm_dashboard_tag</field>  
</record>
<menuitem name="Dashboard" id="crm_dashboard"       sequence="0" action="crm_dashboard_action" parent="crm.crm_menu_root"/>
```

`name= ”tag”` i s the tag that will connect the java script file with our action

Create a `js` file on the `static > src > js > dashboard.js`

```javascript
/**@odoo-module **/  
import { registry } from "@web/core/registry";  
import { Component } from  "@odoo/owl";  
const actionRegistry = registry.category("actions");  
class CrmDashboard extends Component {}  
CrmDashboard.template = "my_module.CrmDashboard";  
//  Tag name that we entered in the first step.  
actionRegistry.add("crm_dashboard_tag", CrmDashboard);
```

```XML
<?xml version="1.0" encoding="UTF-8" ?>  
<templates>  
    <t t-name="my_module.CrmDashboard">  
        <div class="">  
            <div>  
                <center>  
                    <h1 style="margin:20px;">  
                    Crn Dashboard</h1>  
                </center>  
            </div>  
        </div>  
    </t>  
</templates>
```

```manifest
'assets': {  
        'web.assets_backend': [  
            'my_module/static/src/js/dashboard.js',   
            'my_module/static/src/xml/dashboard.xml',  
        ],  
    },
```

Tile
```XML
 <div class="row main-section" style="margin-left: 120px;">  
<!--Lead Tile-->  
	<div id="leads" class="col-md-4 col-sm-6 tot_tasks oh-payslip"  
		 style=" overflow: hidden; padding-top: 30px;">  
		<div class="oh-card" style="box-shadow:2px 4px 8px 2px rgba(0,0,0.3,0.2);  
		display: flex; justify-content: center;" role="button">  
			<div class="oh-card-body"  
				 style="padding: 5px 5px; float: left; width: 100%;  
				  height: auto; box-sizing: border-box; margin: 0;">  
				<div class="stat-widget-one">  
					<div class="stat-icon bg-mauve-light d-flex justify-content-left align-items-left">  
						<div style="background:#ff4d94; width:65px; text-align: center;">  
							<i class="fa fa-tasks text-mauve"  
							   style="font-size:50px;"/>  
						</div>  
						<div class="stat_content" style="  
						  text-align: center; font-weight: bold;  
						  padding-top: 20px; padding-left: 80px;">  
							<div class="stat_count_lead"  
								 style="font-size: 17px;">  
								<span id="templates">  
									 <div id="my_lead"/>  
								</span>  
							</div>  
							<div class="stat-head"  
								 style="font-size: 14px;">My Leads  
							</div>  
						</div>  
					</div>  
				</div>  
			</div>  
		</div>  
	</div>  
<!--Opportunity Tile-->  
	<div id="opportunity" class="col-md-4 col-sm-6 tot_tasks oh-payslip"  
		 style=" overflow: hidden; padding-top: 30px;">  
		<div class="oh-card" style="box-shadow:2px 4px 8px 2px rgba(0,0,0.3,0.2);  
		display: flex; justify-content: center;" role="button">  
			<div class="oh-card-body"  
				 style="padding: 5px 5px; float: left; width: 100%;  
				  height: auto; box-sizing: border-box; margin: 0;">  
				<div class="stat-widget-one">  
					<div class="stat-icon bg-mauve-light d-flex justify-content-left align-items-left">  
						<div style="background:yellow; width:65px; text-align: center;">  
							<i class="fa fa-trophy  text-mauve"  
							   style="font-size:50px;"/>  
						</div>  
						<div class="stat-content" style="  
						  text-align: center; font-weight: bold;  
						  padding-top: 20px; padding-left: 80px;">  
							<div class="stat_count_opp"  
								 style="font-size: 17px;">  
								<span id="templates">  
									 <div id="my_opportunity"/>  
								</span>  
							</div>  
							<div class="stat-head"  
								 style="font-size: 14px;">My Opportunity  
							</div>  
						</div>  
					</div>  
				</div>  
			</div>  
		</div>  
	</div>  
<!--Expected Revenue -->  
	<div id="expected_revenue"  
		 class="col-md-4 col-sm-6 tot_tasks oh-payslip"  
		 style=" overflow: hidden; padding-top: 30px;">  
		<div class="oh-card" style="box-shadow:2px 4px 8px 2px rgba(0,0,0.3,0.2);  
		display: flex; justify-content: center;" role="button">  
			<div class="oh-card-body"  
				 style="padding: 5px 5px; float: left; width: 100%;  
				  height: auto; box-sizing: border-box; margin: 0;">  
				<div class="stat-widget-one">  
					<div class="stat-icon bg-mauve-light d-flex justify-content-left align-items-left">  
						<div style="background:#bf80ff;; width:65px; text-align: center;">  
							<i class="fa fa-usd  text-mauve"  
							   style="font-size:50px;"/>  
						</div>  
						<div class="stat-content" style="  
						  text-align: center; font-weight: bold;  
						  padding-top: 20px; padding-left: 80px;">  
							<div class="stat_count_ex_rev"  
								 style="font-size: 17px;">  
								<span id="templates">  
									 <div id="revenue"/>  
								</span>  
							</div>  
							<div class="stat-head"  
								 style="font-size: 14px;">Expected  
								revenue  
							</div>  
						</div>  
					</div>  
				</div>  
			</div>  
		</div>  
	</div>  
</div>
```

The data to the dashboard is fetched from the `js` file using `ORM.call` method  as follows:
```Javascript
/**@odoo-module **/
import { registry } from "@web/core/registry";
import { useService } from "@web/core/utils/hooks";
import { Component } from  "@odoo/owl";
const actionRegistry = registry.category("actions");
class CrmDashboard extends Component {
   setup() {
         super.setup()
         this.orm = useService('orm')
         this._fetch_data()
   }
   _fetch_data(){
   var self = this;
  this.orm.call("crm.lead", "get_tiles_data", [], {}).then(function(result){
           $('#my_lead').append('<span>' + result.total_leads + '</span>');
           $('#my_opportunity').append('<span>' + result.total_opportunity + '</span>');
           $('#revenue').append('<span>' + result.currency + result.expected_revenue + '</span>');
           });
       };
}
CrmDashboard.template = "my_module.CrmDashboard";
//  Tag name that we entered in the first step.
actionRegistry.add("crm_dashboard_tag", CrmDashboard);
```

As you can see, the function` get_tiles_data() `is used to get the data from the model `crm.lead`.The code will be like this:

```Python
class CrmLead(models.Model):  
    """crm inherited model"""  
    _inherit = 'crm.lead'  
    @api.model  
    def get_tiles_data(self):  
        """ Return the tile data"""  
        company_id = self.env.company  
        leads = self.search([('company_id', '=', company_id.id),  
                             ('user_id', '=', self.env.user.id)])  
        my_leads = leads.filtered(lambda r: r.type == 'lead')  
        my_opportunity = leads.filtered(lambda r: r.type == 'opportunity')  
        currency = company_id.currency_id.symbol  
        expected_revenue = sum(my_opportunity.mapped('expected_revenue'))  
        return {  
            'total_leads': len(my_leads),  
            'total_opportunity': len(my_opportunity),  
            'expected_revenue': expected_revenue,  
            'currency': currency,  
        }
```


[Cybrosys](https://www.cybrosys.com/blog/how-to-create-a-dashboard-in-odoo-17)
