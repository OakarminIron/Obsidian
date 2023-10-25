Drop downs are surprisingly complicated components. They need to provide many features such as:

-   Toggle the item list on click    
-   Direct siblings drop downs: when one is open, toggle others on hover    
-   Close on outside click    
-   Optionally close the item list when an item is selected    
-   Call a function when the item is selected    
-   Support sub drop downs, up to any level    
-   Style it yourself    
-   Configurable hotkey to open/close a drop down or select a drop down item    
-   Keyboard navigation (arrows, tab, shift+tab, home, end, enter and escape)    
-   Reposition itself whenever the page scrolls or is resized    
-   Smartly chose the direction it should open (right-to-left direction is automatically handled).


| Dropdown     | Type                  | Description                                                                                                                                                                                                         |
|--------------|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| startOpen    | boolean               | initial dropdown open state (defaults to false)                                                                                                                                                                     |
| menuClass    | string                | additional css class applied to the dropdown menu <div class="dropdown-menu"/>                                                                                                                                      |
| togglerClass | string                | additional css class applied to the toggler <button class="dropdown-toggle"/>                                                                                                                                       |
| hotkey       | string                | hotkey to toggle the opening through keyboard                                                                                                                                                                       |
| tooltip      | string                | add a tooltip on the toggler                                                                                                                                                                                        |
| beforeOpen   | function              | hook to execute logic just before opening. May be asynchronous.                                                                                                                                                     |
| manualOnly   | boolean               | if true, only toggle the dropdown when the button is clicked on (defaults to false)                                                                                                                                 |
| disabled     | boolean               | disable (if true) the dropdown button (defaults to false)                                                                                                                                                           |
| title        | string                | title attribute content for the <button class="dropdown-toggle"/> (default: none)                                                                                                                                   |
| position     | string                | defines the desired menu opening position. RTL direction is automatically applied. Should be a valid usePosition hook position. (default: bottom-start)                                                             |
| toggler      | "parent" or undefined | when set to "parent" the <button class="dropdown-toggle"/> is not rendered (thus toggler slot is ignored) and the toggling feature is handled by the parent node (e.g. use case: pivot cells). (default: undefined) |

| DropdownItem      | Type                 | Description                                                                                                                                                                                   |
|-------------------|----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| onSelected        | Function             | a function that will be called when the dropdown item is selected.                                                                                                                            |
| parentClosingMode | none \| closest | all | when the item is selected, control which parent dropdown will get closed: none, closest or all (default = all)                                                                                |
| hotkey            | string               | optional hotkey to select the item                                                                                                                                                            |
| href              | string               | if provided the DropdownItem will become an <a href="value" class="dropdown-item"/> instead of a <span class="dropdown-item"/>. (default: not provided)                                       |
| title             | string               | optional title attribute which will be passed to the root node of the DropdownItem. (default: not provided)                                                                                   |
| dataset           | Object               | optional object containing values that should be added to the root element’s dataset. This can be used so that the element is easier to find programmatically, for example in tests or tours. |


Direct Siblings Dropdown
Multi-level Dropdown