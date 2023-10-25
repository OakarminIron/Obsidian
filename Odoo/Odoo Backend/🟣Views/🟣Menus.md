```
<menuitem id="root_custom_app" name="Custom"/>
<menuitem id="custom_menu1" name="Menu1" action="action_id" parent="root_custom_app"/>

<menuitem id="custom_menu1_othermodule" name="Menu1" action="action_id" parent="othermodule.menuid"/>
needs to inherit in __manifest__.py
```

Menu - Name of the menu
Parent Menu - The parent menu
Sequence - Sequence of the menu item.
Action - Specify the action.
Access Rights - Giving access privileges allows you to restrict access to a certain user group
