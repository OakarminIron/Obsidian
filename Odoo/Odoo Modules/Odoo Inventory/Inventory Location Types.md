https://www.cybrosys.com/blog/location-types-odoo-12

[[Internal Location]]: Physical locations inside your own warehouses,
[[Transit Location]]: Counterpart location that should be used in inter-company or inter-warehouses operations"

Virtual Locations
- [[Inventory Location Vendor]]: Representing the source location for products coming from your vendors
- [[Inventory Location View]]:  Used to create a hierarchical structures for your warehouse, aggregating its child locations ; can't directly contain products
- [[Inventory Location Customer]]:  Representing the destination location for products sent to your customers
- [[Inventory Inventory Loss]]: Serving as counterpart for inventory operations used to correct stock levels (Physical inventories)
- [[Inventory Location Procurement]]: Serving as temporary counterpart for procurement operations when the source (vendor or production) is not known yet. This location should be empty when the procurement scheduler has finished running.
- [[Inventory Location Production]]: Virtual counterpart location for production operations: this location consumes the raw material and produces finished products

