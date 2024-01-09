
```XML
<odoo>
	<record id="contact_menu" model="website.menu">
    	<field name="name">Contacts</field> <!-- Name of the menu-->
    	<field name="url">/contacts</field>
    	<field name="parent_id" ref="website.main_menu"/>
	</record>
	<template id="contact_details_template" name="Contact Details">
    	<t t-call="website.layout">
			----
    	</t>
	</template>
</odoo>
```

`QWeb` Inherit

* `t-inherit`:-This directive is used to specify the name of the template to inherit from. In other words, it defines the parent template.
* `t-inherit-mode`:- This directive determines the behaviour of inheritance and has two modes:
	* Primary Mode:Used to create a new child template from the parent template. This implies that the child template inherits the structure and possibly some content from the parent.
	* Extension Mode:Used to modify the parent template and alter information or data. This means that the child template extends or overrides certain sections of the parent template.
- `t-name`:- This directive is optional, and its purpose is not clear from the provided information. It may be used to assign a name to the template.

```XML
<?xml version="1.0" encoding="UTF-8" ?>  
<templates xml:space="preserve">  
    <t t-name="this_module_name.this_template_name"  
     t-inherit="parent_module.template_name"  
     t-inherit-mode="primary">  
	 <xpath expr="//div[hasclass('dashboard-heading')]"   position="replace">  
		Do some shit
	 </xpath>  
    </t>  
</templates>
```

[[🟣xpath]]
[Cybrosys](https://www.cybrosys.com/blog/an-overview-of-template-inheritance-in-odoo-16)
