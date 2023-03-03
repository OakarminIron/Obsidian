## Functional

Odoo being the open source ERP software with its simplicity and extensibility gained its popularity among the small to large scale industries after its first release. And ORM methods are one of its strong features which helps in executing SQL queries without writing them down explicitly. With the help of ORM methods, the user can implement the OOPS concepts to interact with the database i.e. ORM fills the gap between the database and the OOP classes and objects.

With the help of ORM, we can easily manage the creation of tables and fields based on the class definition that we provide for the model. Based on the definition, Odoo creates and manages tables for us inside the database. Thus reducing our work of creation of tables using the queries. Also this helps the developers to concentrate on the business logic of the application as less codes are required for developing the CRUD part of the application, also load on the application.

Now let us discuss some of the common ORM methods.

The common ORM methods in Odoo are listed below.

1. create()

The create() method is used to create new records for the model. This method accepts a set of dictionary values and new records are initialized with it.

Syntax: Model.create(vals_list) ? records


This creates a new recordset in the current model with name Cybrosys and email as demo@cybrosys.com

2. copy()

The copy() method is used to duplicate a recordset in the current model. This method accepts only the default argument.

Syntax: Model.copy(default=None) ? new record

Eg: new_record = self.copy()

This creates and returns a copy of the current active record in the model.

3. write()

The write() method is used to update the records inside the model with the provided values. This method accepts a set of dictionary values and the record is updated with these values.

Syntax: Model.write(vals) ? updated record



This updates the current records email field with value demo@cybrosys.info

4. browse()

The browse() method is used to return a set of records for the IDs passed as the parameter in the current working model. This method accepts a set of IDs and returns the recordsets corresponding to that IDs.

Syntax: Model.browse([ids]) ? records

Eg: self.browse([7, 18, 12])

This returns the records with IDs 7, 18 and 12 of the corresponding model.

5. search()

The search() method is used to search records within the given model based on the search domain passed as the argument. This method accepts a search domain to check for matching conditions inside the model and returns the recordsets.

Syntax: Model.search(args[, offset=0][, limit=None][, order=None][, count=False]) -> records

If no argument is provided as the search domain, all the records are matched and returned.

The offset defines the number of records to be ignored, limit defines the maximum number of records to be returned, order defines the sort string and count if set as true only returns the count of records matching the domain condition.

Eg: self.search([('is_company', '=', True)], limit=1)

6. search_count()

The search_count() method returns the number of records matching the search domain. This method accepts a search domain as its arguments.

Syntax: Model.search_count(args) ? int

Eg: self.search_count([('product_tmpl_id', '=', record.product_tmpl_id.id),('active', '=', True), ])

This returns the set of records satisfying the domain conditions given as the arguments inside the model.

7. unlink()

The unlink method is used to remove the recordset from the model. The unlink method does not take any argument, it removes the current active record of the model.

Syntax: Model.unlink()

Eg: self.unlink()

This deletes the record currently inside the self.

8. exists()

The exists() method returns the subset of records that exists in self. It returns a recordset which contains only the records that exist in the database. It can also be used to check whether a particular record still exists.

Syntax: Model.exists() ? records

Eg: 

if not rec.exists():

    raise Exception("The record has been deleted")

9. ensure_one()

The ensure_one() method checks whether the recordset holds only a single record, otherwise raises an exception.

Syntax: Model.ensure_one()

10. filtered()

The filtered method returns a set of records which satisfies the function given as argument. This method accepts a function as its argument.

Syntax: Model.filtered(func) ? records

Eg: records.filtered(lambda r: r.company_id == user.company_id)

This only keeps records whose company is the current user's.

11. mapped()

The mapped() function applies the function given as an argument on all the records in the self, and then returns the result as a list or recordset. This method accepts a function as its argument.

Syntax: Model.mapped(func) ? recordset / list

Eg: records.mapped(lambda r: r.field1 + r.field2)

This returns a list of summing two fields for each record in the set

12. sorted()

The sorted() method returns the records inside the self, ordered by the key passed as the argument.

Syntax: Model.sorted(key=None, reverse=False)

If reverse is set as True, returns the result in reverse order.

Eg: records.sorted(key=lambda r: r.name)

Sorts the record based on the name field.

  

To explore more about Odoo ORM, do check out our blog on [ORM in Odoo](https://www.cybrosys.com/blog/orm-in-odoo)