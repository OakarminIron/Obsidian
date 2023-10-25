First of all, components are classes, so they have a constructor. But constructors are special methods in javascript that are not overridable in any way. Since this is an occasionally useful pattern in Odoo, we need to make sure that no component in Odoo directly uses the constructor method. Instead, components should use the `setup` method:


https://www.odoo.com/documentation/master/developer/reference/frontend/owl_components.html
| Technical Name | Short Description                                        |
|----------------|----------------------------------------------------------|
| [[🦉ActionSwiper]]   | a swiper component to perform actions on touch swipe     |
| CheckBox       | a simple checkbox component with a label next to it      |
| [[🦉ColorList ]]     | a list of colors to choose from                          |
| [[🦉Dropdown]]       | full-featured dropdown                                   |
| Notebook       | a component to navigate between pages using tabs         |
| Pager          | a small component to handle pagination                   |
| SelectMenu     | a dropdown component to choose between different options |
