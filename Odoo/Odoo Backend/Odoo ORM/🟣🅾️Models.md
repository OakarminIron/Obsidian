Model fields are defined as attributes on the model itself

``` python
from odoo import models, fields
class AModel(models.Model):
    _name = 'a.model.name'

    field1 = fields.Char()
```
[[🟣🅾️Inheritance👨‍👦]]


-------------------------------------
Base Model
```python
class BaseModel(metaclass=MetaModel):
    """Base class for Odoo models.
```
[Github](https://www.odoo.com/documentation/17.0/developer/reference/backend/orm.html#odoo.models.BaseModel)
Models are created by inheriting one of the following:

*   :class:`Model` for regular database-persisted models.
*   :class:`TransientModel` for temporary data, stored in the database but automatically vacuumed every so often.
*   :class:`AbstractModel` for abstract super classes meant to be shared by multiple inheriting models.
