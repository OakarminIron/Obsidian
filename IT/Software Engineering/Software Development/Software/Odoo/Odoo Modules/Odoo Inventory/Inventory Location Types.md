https://www.cybrosys.com/blog/location-types-odoo-12


Vendor Location: Virtual location representing the source location for products coming from your vendors

View: Virtual location used to create a hierarchical structures for your warehouse, aggregating its child locations ; can't directly contain products

Internal Location: Physical locations inside your own warehouses,

Customer Location: Virtual location representing the destination location for products sent to your customers

Inventory Loss: Virtual location serving as counterpart for inventory operations used to correct stock levels (Physical inventories)

Procurement: Virtual location serving as temporary counterpart for procurement operations when the source (vendor or production) is not known yet. This location should be empty when the procurement scheduler has finished running.

Production: Virtual counterpart location for production operations: this location consumes the raw material and produces finished products

Transit Location: Counterpart location that should be used in inter-company or inter-warehouses operations"