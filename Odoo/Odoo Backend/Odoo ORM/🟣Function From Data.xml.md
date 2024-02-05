``` xml
<odoo>  
	<data noupdate="1">  
		<function model="product.template" name="my_product"/>
		<function model="product.template" name="func_with_params">  
			<value>Calculator</value>  
		</function>
	</data>  
</odoo>
```

```python
from odoo import models, fields, api  
class ProductTemplate(models.Model):  
	_inherit = "product.template"  
	@api.model  
	def my_product(self):  
	  self.create(dict(name='My Product'))
	
	def func_with_params(self, value):  
	  self.create(dict(name=value))
```

