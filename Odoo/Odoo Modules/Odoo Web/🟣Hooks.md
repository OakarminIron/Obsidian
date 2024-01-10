
```xml
'uninstall_hook': 'uninstall_hook'
'pre_init_hook': 'pre_init_hook',
'post_init_hook': 'create_field',
'post_load': 'post_load'
```

in `init.py`
```python
def create_field(cr):  
	cr.execute(""" ALTER TABLE "res_partner"  ADD COLUMN "xxx" VARCHAR""")

