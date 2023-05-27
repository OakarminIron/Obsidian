`@http.route`  is a decorator which allows navigating to the URL specified in it.

`@http.route('/contacts', type='http', auth='public', website=True)`

Inside `http.route()`, we can define some parameters like
 - [[🟣🎛️URL]]`/url`: In this keyword, we need to specify the url that needs to be redirected.In the above example, `/contacts` is the url
 - [[🟣🎛️type]]`type`: The type keyword defines which kind of operation needs to be performed. type can have two values
	 - `type=’http’`  will return to the template, and it will take the dictionary with that. 
	 - `type='json'` will call from json rpc from JavaScript.
 - [[🟣🎛️auth]]`auth`: auth describes who can access the specified URL. It can have values like
	 - auth=’public’: anyone can access the url, no restrictions.
	 - auth=’user’: the logged-in user has only permission to access the url.
	 - auth=’none’: it is always active and mainly used by the authentication modules.
- [[🟣🎛️website]]`website`: this keyword describes whether this controller links to a web page or not. It can be True or False.
- [[🟣🎛️methods]]  – A list of http methods (verbs) this route applies to. If not specified, all methods are allowed.
- [[🟣🎛️cors]]   `cors (str)` – The Access-Control-Allow-Origin cors directive value.
- [[🟣🎛️csrf]]     `csrf (bool)` – Whether CSRF protection should be enabled for the route. Enabled by default for 'http'-type requests, disabled by default for 'json'-type requests.