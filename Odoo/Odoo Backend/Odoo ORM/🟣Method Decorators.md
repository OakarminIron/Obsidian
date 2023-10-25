Decorators are a powerful tool by python, which allows modifying the behavior of a function, method, or class. Odoo uses decorators to specify what the undertaking function is and what are the data(record-set) contained. Decorators are regarded as highly useful while considering migration from the old version to the new. Methods written in the traditional API style will be automatically converted to the record style in the newer versions. These decorators are described in the apy.py file. Major decorators are :

1. [[api.multi]]
2. [[api.one()]]
3. [[api.model()]]
4. [[api.multi()]]
5. [[api.depends(arguments)]]
6. [[api.constraints(arguments)]]
7. [[api.onchange(arguments)]]
8.[[ api.return]](model=””, upgrade=None, downgrade=None)