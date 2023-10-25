Odoo assets are grouped by bundles. Each bundle (a list of file paths of specific types: xml, js, css or scss) is listed in the module manifest. Files can be declared using glob syntax, meaning that you can declare several asset files using a single line.
The bundles are defined in each module’s __manifest__.py, with a dedicated assets key which contains a dictionary. The dictionary maps bundle names (keys) to the list of files they contain (values). It looks like this:

```
'assets': {
    'web.assets_backend': [
        'web/static/src/xml/**/*',
    ],
    'web.assets_common': [
        'web/static/lib/bootstrap/**/*',
        'web/static/src/js/boot.js',
        'web/static/src/js/webclient.js',
    ],
    'web.qunit_suite_tests': [
        'web/static/src/js/webclient_tests.js',
    ],
},
```

