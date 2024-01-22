[[🟣🅾️👨‍👦Classical]]
The attribute `_name` was the only one declared in the parent class; however, the child class defined both `_name` and `_inherit`, allowing the child model to access the parent class's fields and functions.

```Python
class ClassicalInheritanceParent(models.Model):  
   _name = 'classical.inheritance.parent'  
   _description = 'Classical Inheritance Parent'  
   name = fields.Char(string="Name")  
   def call(self):  
       return self.test_check("Model ClassicalInheritanceParent")  
   def test_check(self, s):  
       return "This is a test check with {}".format(s)  
class ClassicalInheritanceChild(models.Model):  
   _name = 'inheritance.child'  
   _inherit = 'classical.inheritance.parent'  
   _description = 'Classical Inheritance Child'  
   def call(self):  
       return self.test_check("Model ClassicalInheritanceChild")
```

[[🟣🅾️👨‍👦Extension]]- Just use the `_inherit` attribute and not the `_name` attribute. The previous model is also replaced by the new one. 

``` python
class Extension(models.Model):  
   _name = 'extension.extension'  
   _description = 'Extension Extension'  
   name = fields.Char(default="Name")  
  
class Extension(models.Model):  
   _inherit = 'extension.extension'  
   description = fields.Char(default="Extended"
```


[[🟣🅾️👨‍👦Delegation]]
This kind of inheritance also allows you to **sink** another model to your current model without changing the views.
As a result, the database tables will have both a field for the inherited object and the information from your model. 
```Python
class ProductTemplate(models.Model):  
   _name = "product.template"  
  
class ProductProduct(models.Model):  
   _name = "product.product"  
   _inherits = {'product.template': 'product_tmpl_id'}  
  
product_tmpl_id = fields.Many2one('product.template', 'Product Template', required=True, ondelete="cascade")
```



for OWL Inheritance go to [[🦉Inheritance]]