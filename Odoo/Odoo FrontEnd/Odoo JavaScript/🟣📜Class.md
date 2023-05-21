Creating a subclass
```
var Class = require('web.Class');

var Animal = Class.extend({
    init: function () {
        this.x = 0;
        this.hunger = 0;
    },
    move: function () {
        this.x = this.x + 1;
        this.hunger = this.hunger + 1;
    },
    eat: function () {
        this.hunger = 0;
    },
});
```
Inheritance
```
var Animal = require('web.Animal');

var Dog = Animal.extend({
    move: function () {
        this.bark();
        this._super.apply(this, arguments);
    },
    bark: function () {
        console.log('woof');
    },
});

var dog = new Dog();
dog.move()
```

Mixins
```
var Animal = require('web.Animal');
var DanceMixin = {
    dance: function () {
        console.log('dancing...');
    },
};

var Hamster = Animal.extend(DanceMixin, {
    sleep: function () {
        console.log('sleeping');
    },
});
```