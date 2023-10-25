
[[🟣🍱Odoo Assets]] are grouped by bundles, where each bundle can be a list of different file paths for specific asset types such as XML, Java-script, CSS, and `SCSS`.
Bundles are listed in the Odoo module's manifest file.
These files use a global syntax, so one line declares the various files containing the assets.

1. [[web.assets_common]]
2. [[web.assets_backend]]
3. [[web.assets_frontend]]
4. [[web.assets_qweb]]:All static XML templates are used in the back end environment and Point of Sale.
5. [[web.qunit_suite_tests]]:All JavaScript unit test code (tests, helpers, mocks).
6. [[web.qunit_mobile_suite_tests]]:Mobile-specific unit test code.

```
'assets': {
   'web.assets_common': [
       'web/static/lib/bootstrap/**/*',
       'web/static/src/js/boot.js',
       'web/static/ src/js/webclient.js',
   ],
   'web.assets_backend': [
       'web/static/src/xml/**/*',
   ],
   'web.assets_frontend': [
       'web/static/src/scss/style.scss',
       'web/static/src/js/custom.js',
   ],
   'web.assets_qweb': [
       'web/static/src/xml/templates.xml',
   ],
   'web.qunit_suite_tests': [
       'web/static/src/js/webclient_tests.js',
   ],
   'web.qunit_mobile_suite_tests': [
       'web/static/tests/mock_tests.js',
   ],
},
```


