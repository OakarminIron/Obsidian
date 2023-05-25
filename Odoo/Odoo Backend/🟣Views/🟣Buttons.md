
Python
```
xfield = fields.12m or m2m
xcounts = fields.Integer(compute="_compute_count", string='Counts')
def _compute_count(self):
	for record in self:	
		record.xcounts = self.xfield.search_count([('yfield', '=', record.id)])

def btn_python_function(self):
	self.ensure_one()
	xml_id = self.env.context.get('xml_id')
	if xml_id:
		res = self.env['ir.actions.act_window']._for_xml_id('module.action_id')
		res.update(
			context=dict(self.env.context, default_yfield =self.id, group_by=False),
			domain=[('yfield', '=', self.id)]	
		)
	return res
return False
```
XML Form
```
<button name="python_function" string="Click" class="oe_highlight" type="object"/>

<button name="python_function" type="object" class="oi oi-view-list" context="{'xml_id':'action_id'}">
	<field name="xcounts" widget="statinfo" string="Clicky"/>
</button>

```
XML Tree
```
<field name="xcounts" widget="statinfo" string="Counts"/>
<button name="btn_python_function" type="object" icon="fa-list" context="{'xml_id':'module.action_id'}">
```
