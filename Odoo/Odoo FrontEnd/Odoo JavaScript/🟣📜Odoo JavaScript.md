The Odoo JavaScript framework is a set of features/building blocks provided by the `web/` addon to help build odoo applications running in the browser. 
At the same time, the Odoo JavaScript framework is a single page application, usually known as the **_web client_** (available at the url `/web`).
The web client started as an application made with a custom class and widget system, but it is now transitioning to using native [[📜JavaScript]] classes instead, and [[🦉OWL Framework]] as a component system. 
This explains why both systems are currently in use in the codebase.
From a high-level perspective, the web client is a single-page application: it does not need to request a full page from the server each time the user performs an action. Instead, it only requests what it needs and then replaces/updates the current screen accordingly. Also, it manages the url to keep it in sync with the current state.
The JavaScript framework (all or some parts) is also used in other situations, such as the Odoo website or the point of sale. This reference is mostly focused on the web client.

[[🟣📜Assets]]
[[🟣📜Registries]]
[[🟣📜Web Client]]
[[🟣📜Class]]
[[🟣📜Widget]]