'post_init_hook': 'create_field',
in init.py
def create_field(cr):  
cr.execute("""  ALTER TABLE "res_partner"  ADD COLUMN "xxx" VARCHAR""")

'uninstall_hook': 'uninstall_hook'
'pre_init_hook': 'pre_init_hook',
'post_load': 'post_load'