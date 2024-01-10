`_class_ odoo.api.Environment(_cr_, _uid_, _context_, _su=False_)` [source](https://github.com/odoo/odoo/blob/17.0/odoo/api.py#L471)
The environment can be used to get an empty record-set in an other model, and query that model:
`record.env[]`
The environment stores various contextual data used by the `ORM`:
```
	- :attr:`cr`: the current database cursor (for database queries);
	- :attr:`uid`: the current user id (for access rights checks);
	- :attr:`context`: the current context dictionary (arbitrary metadata);
	- :attr:`su`: whether in superuser mode.
```
`cr.execute`

[[Environment(function)]]
[[Environment_Altering]]
