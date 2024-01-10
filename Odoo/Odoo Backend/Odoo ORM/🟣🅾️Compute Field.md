
- `precompute (bool)` -whether the field should be computed before record insertion in database. 
- `compute_sudo (bool)` – whether the field should be recomputed as superuser to bypass access rights
- `recursive (bool)` – whether the field has recursive dependencies (the field X has a dependency like parent_id.X)
- `inverse (str)` – name of a method that inverses the field
- `search (str)` – name of a method that implement search on the field
- `related (str)` – sequence of field names
- `default_export_compatible (bool)` –whether the field must be exported by default in an import-compatible export

examples

```python
description = fields.Char("Description", required=True,compute="_compute_description", store=True, readonly=False, precompute=True)
gross_increase_value = fields.Monetary(string="Gross Increase Value", compute="_compute_book_value", compute_sudo=True)
book_value = fields.Monetary(string='Book Value', readonly=True, compute='_compute_book_value', recursive=True, store=True,)
employee_ids = fields.Many2many('hr.employee', string='Employees',compute='_compute_employee_ids', inverse='_inverse_employee_ids')
sdd_has_usable_mandate = fields.Boolean(compute='_compute_sdd_has_usable_mandate', search='_search_sdd_has_usable_mandate')
name = fields.Char("Name", index='trigram', required=True, tracking=True, translate=True, default_export_compatible=True)
```

