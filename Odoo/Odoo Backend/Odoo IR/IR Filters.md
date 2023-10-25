IR Filters allow users to define reusable filters that can be applied to different views to quickly narrow down the displayed records. They provide a convenient way to save and apply specific search criteria within Odoo.

IR Filters in Odoo are a feature that allows users to define reusable filters to quickly narrow down the displayed records in various views. They provide a convenient way to save specific search criteria for future use. Here are some key points about IR Filters:

1. Definition: An IR Filter is a saved search query that can be applied to different views within Odoo. It consists of specific conditions or rules that define which records should be displayed.    
2. Usage: IR Filters are commonly used in list views, kanban views, and search views in Odoo. They enable users to quickly filter and sort records based on specific criteria without having to manually set up the filters each time.    
3. Creation: Users can create an IR Filter by applying desired search criteria within a view and then saving that search as a filter. The filter can be given a name for easy identification and future use.    
4. Customization: IR Filters can be customized based on individual preferences. Users can specify the filter conditions, including fields to search, comparison operators, and field values to match. Multiple conditions can be combined using logical operators like AND and OR.    
5. Re-usability: Once an IR Filter is saved, it can be reused in different views and accessed by other users who have the necessary access rights. This promotes consistency in filtering data across the system and enables users to easily switch between different saved filters.    
6. Editing and Deletion: Users have the flexibility to edit or delete existing IR Filters. They can modify the filter conditions or delete filters that are no longer needed. This allows for the management and maintenance of filters based on changing requirements.    
7. Default Filters: In addition to user-defined filters, Odoo also provides default filters that are pre-configured based on common scenarios. These default filters offer quick access to frequently used search criteria, such as "My Records" or "Today's Tasks."    
```
<record id="hr_applicant_filter_recruiter" model="ir.filters">
	<field name="name">By Recruiter</field>	
	<field name="model_id">hr.applicant</field>	
	<field name="user_id" eval="False"/>	
	<field name="action_id" ref="hr_applicant_action_analysis"/>	
	<field name="context">{'group_by': ['create_date:month', 'user_id']}</field>
</record>
```
By leveraging IR Filters, users can streamline their workflow, save time, and focus on the specific data they need to work with. It enhances the user experience by providing a customization able and efficient way to filter and view relevant records in Odoo.