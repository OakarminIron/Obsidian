Registries are (ordered) key/value maps. They are the main web client extension points: many features provided by the Odoo javascript framework simply look up into a registry whenever it needs a definition for some object (such as fields, views, client actions or services). Customizing the web client is then simply done by adding specific values in the correct registry.

```
import { Registry } from "@web/core/registry";

const myRegistry = new Registry();

myRegistry.add("hello", "odoo");

console.log(myRegistry.get("hello"));
```
A useful feature of registries is that they maintain a set of sub registries, obtained by the `category` method. If the sub registry does not exist yet, it is created on the fly. All registries used by the web client are obtained in such a way from one root registry, exported in `@web/core/registry`.

Registry API
Reference List
Effect registry
Formatter registry