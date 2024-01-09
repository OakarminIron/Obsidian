https://www.cybrosys.com/blog/location-types-odoo-12

**Physical Location**
	The internal location includes the physical place. 
	Since the internal locations would be found inside the warehouse, we have assigned an internal location's short name, `WH`, to stand for Warehouse.
	Our internal locations are where we keep our products in our inventory of `Odoo`. 
	This space is also used for loading products out of the warehouse and unloading supplies into the warehouse.
		[[🟣🏬Internal]]: Physical locations inside your own warehouses,
		[[🟣🏬Transit]]: Counterpart location that should be used in inter-company or inter-warehouses operations"


**Partner Location**
	The partners' location is known as the partner location. A vendor or consumer could be a partner. 
	The customer or vendor would be the owner of these locations, which would be outside your warehouse. Still, these places function in the same manner as our actual locales.
		[[🟣🏬Customer]]:  Representing the destination location for products sent to your customers
		[[🟣🏬Vendor]]: Representing the source location for products coming from your vendors

**Virtual Locations**
	Besides a physical site, businesses run virtual locations to simulate an actual warehouse. 
	As the name suggests, a virtual location only exists in theory. 
	Products that aren't physically stored in the inventory may be kept here.
	 [[🟣🏬View]]:  Used to create a hierarchical structures for your warehouse, aggregating its child locations ; can't directly contain products
	 [[🟣🏬Inventory Loss]]: Serving as counterpart for inventory operations used to correct stock levels (Physical inventories)
	 [[🟣🏬Procurement]]: Serving as temporary counterpart for procurement operations when the source (vendor or production) is not known yet. 
		This location should be empty when the procurement scheduler has finished running.
	 [[🟣🏬Production]]: Virtual counterpart location for production operations: this location consumes the raw material and produces finished products
