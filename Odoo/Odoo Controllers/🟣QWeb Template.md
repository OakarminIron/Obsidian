
```
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