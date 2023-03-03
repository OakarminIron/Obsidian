A Mail Alias is a mapping of an email address with a given Odoo Document model. It is used by Odoo's mail gateway when processing incoming emails sent to the system. If the recipient address (To) of the message matches a Mail Alias, the message will be either processed following the rules of that alias. If the message is a reply it will be attached to the existing discussion on the corresponding record, otherwise a new record of the corresponding model will be created.

This is meant to be used in combination with a catch-all email configuration on the company's mail server, so that as soon as a new mail.alias is created, it becomes immediately usable and Odoo will accept email for it.


[[mail.alias.mixin(abstract)]]
