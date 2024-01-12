To configure the security lead times for your sales and purchase orders, go to the “Advanced Scheduling” tab of the “Settings” window of the “Configuration” 
[Odoo Lead times](https://www.odoo.com/documentation/17.0/applications/inventory_and_mrp/inventory/shipping_receiving/advanced_operations_shipping/scheduled_dates.html#lead-time-types) = [[Lead Time⌛]]  + Security delta for each

- app ‣ Products ‣ Products ‣ Inventory ‣ Lead Time
- Setting  ‣  app ‣ Configuration ‣ Security Lead Time

![[🟣Lead Time.png]]

- **September 1st**: Sales order created, confirmed by salesperson.
- **September 9th**: Deadline to order components to ensure they arrive in time when manufacturing begins (4-day supplier lead time).
- **September 13th**: Scheduled date of receipt for components. Initially, it was set to 9/14, but the 1-day purchase security lead time pushed the date earlier by 1 day.
- **September 14th**: Deadline to begin manufacturing. Calculated by subtracting the manufacturing lead time of 3 days, and the manufacturing security lead time of 2 days, from the expected delivery date of September 19th.
- **September 19th**: Scheduled Date on the delivery order form indicates the updated expected delivery date, which was originally set as September 20th. But the sales security lead time pushed the date forward by a day.