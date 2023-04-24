The _user context_ is a small object containing various information related to the current user.

| Name                | Type     | Description                                               |
|---------------------|----------|-----------------------------------------------------------|
| allowed_company_ids | number[] | the list of active company ids for the user               |
| lang                | string   | the user language code (such as “en_us”)                  |
| tz                  | string   | the user current timezone (for example “Europe/Brussels”) |

In practice, the [[Odoo ORM]] service automatically adds the user context to each of its requests. This is why it is usually not necessary to import it directly in most cases.