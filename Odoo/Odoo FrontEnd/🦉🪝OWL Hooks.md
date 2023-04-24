Owl hooks are a way to factorize code, even if it depends on some component lifecycle. Most hooks provided by Owl are related to the lifecycle of a component, but some of them (such as useComponent) provide a way to build specific hooks.

Using these hooks, it is possible to build many customized hooks that help solve a specific problem, or make some common tasks easier. The rest of this page documents the list of hooks provided by the Odoo web framework.

https://www.odoo.com/documentation/master/developer/reference/frontend/hooks.html#frontend-hooks

| Name          | Short Description                                      |
|---------------|--------------------------------------------------------|
| useAssets     | load assets                                            |
| useAutofocus  | focus automatically an element referenced by autofocus |
| useBus        | subscribe and unsubscribe to a [[env.bus]]                     |
| usePager      | Display the pager of the control panel of a view.      |
| usePosition   | position an element relative to a target               |
| useSpellCheck | activate spellcheck on focus for input or textarea     |
