

Pull Rules are used to fulfil a sales order. Odoo generates a need at the _Customer Location_ for each product in the order. Because pull rules are triggered by a need, Odoo looks for a pull rule defined on the _Customer Location_.
In this case, a “delivery order” pull rule that transfers products from the _Shipping Area_ to the _Customer Location_ is found, and a transfer between the two locations is created.

Then, Odoo finds another pull rule that tries to fulfill the need for the _Shipping Area_: the “packing” rule that transfers products from the _Packing Area_ to the _Shipping Area_. Finally, other pull rules are triggered until a transfer between the _Stock_ and the _Picking Area_ is created.

------------------------
On the other hand, _Push Rules_ are much easier to understand. Instead of generating documents based on needs, they are triggered in real time when products arrive in a specific location. Push rules basically say: “when a product arrives at a specific location, move it to another location.”

An example of a push rule would be: when a product arrives in the _Receipt Area_, move it to the _Storage Location_. As different push rules can be applied to different products, the user can assign different storage locations for different products.

Another push rule could be: when products arrive at a location, move them to the _Quality Control Area_. Then, once the quality check is done, move them to their _Storage Location_.