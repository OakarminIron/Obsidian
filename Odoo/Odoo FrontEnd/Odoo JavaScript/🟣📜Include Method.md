```JavaScript
odoo.define('my_module.MyMixin', function (require) {
    'use strict';
    var core = require('web.core');
    var _t = core._t;
    var MyMixin = {
        myMixinMethod: function () {
            // Mixin method implementation
        },
    };
    return MyMixin;
});
odoo.define('my_module.MyClassExtension', function (require) {
    'use strict';
    var core = require('web.core');
    var MyClass = require('some.module.MyClass');
    var MyMixin = require('my_module.MyMixin');
    var _t = core._t;
    MyClass.include(MyMixin);
    return MyClass;
});
```
In this example, we define a mixin my_module.MyMixin provides the myMixinMethod. 
Then, we use the include method to include this mixin into the MyClass from the some.module.MyClass. 
The `myMixinMethod` is now available in `MyClass` and can be used by instances of `MyClass`.

=============================================================
```JavaScript
odoo.define('my_module.GenericBehavior', function (require) {
    'use strict';
    var core = require('web.core');
    var _t = core._t;
    var GenericBehavior = {
        genericMethod: function () {
            // Generic behaviour implementation
        },
    };
```
add generic behavior to multiple class
