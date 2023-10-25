The _Widget_ class is really an important building block of the user interface. Pretty much everything in the user interface is under the control of a widget. The Widget class is defined in the module _web.Widget_, in _widget.js_.

In short, the features provided by the Widget class include:

-   parent/child relationships between widgets (_PropertiesMixin_)    
-   extensive life-cycle management with safety features (e.g. automatically destroying children widgets during the destruction of a parent)    
-   automatic rendering with QWEB    
-   various utility functions to help interacting with the outside environment.

```
var Widget = require('web.Widget');

var Counter = Widget.extend({
    template: 'some.template',
    events: {
        'click button': '_onClick',
    },
    init: function (parent, value) {
        this._super(parent);
        this.count = value;
    },
    _onClick: function () {
        this.count++;
        this.$('.val').text(this.count);
    },
});
```

[[🟣📜Widget Life-cycle]]

