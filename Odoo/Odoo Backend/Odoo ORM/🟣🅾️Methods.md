The common `ORM` methods in Odoo are listed below.

- [[🟣🅾️create()]]
- [[🟣🅾️copy()]]
- [[🟣🅾️write()]]


- [[🟣🅾️filtered()]] Helps to optimise and simplify the code by avoiding unwanted loop conditions to reach the condition.
	- `supplier_ids = partner_ids.filtered(lambda l: l.supplier)`
- [[🟣🅾️read]] Fetch the values of fields from one or more records. It requires a list of record IDs and a list of field names to be read.
	- `self.env['res.partner'].browse(self.partner.id).read()`
- [[🟣🅾️mapped()]] The mapped method iterates through each record in the source_record-set, applies the specified `func` function, and gathers the outcomes in a fresh record-set called result_record-set.
	- `invoices = self.mapped('invoice_ids')`
- [[🟣🅾️browse()]] Fetch records from the database using their IDs, yielding a record-set that encapsulates the identified records.
	- `partner = self.env['res.partner'].browse(partner_id)`
- [[🟣🅾️search()]]  Locate records based on specified conditions, providing a list of record ids that meet the search criteria.
	- `customer = self.env['res.partner'].search([('id', '=', rec.partner_id.id)])`
- [[🟣🅾️search_count()]]
- [[🟣🅾️sorted()]] ` self.line_ids = self.line_ids.sorted(key=lambda x: x.product_id.name)`



- [[🟣🅾️unlink()]]
- [[🟣🅾️flush()]]

