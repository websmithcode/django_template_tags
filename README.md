# django_template_tags
Custom template tags for django.

> Adds tags such, as: "multiply", "range"  
> Before use needs load {% load common_tags %}

For install:  
Add "templateteags" dit to your application and register "common_tags" in the settings to "TEMPLATES" > "libraries":
       
       TEMPLATES = [
            {
                'BACKEND': '...',
                'DIRS': [...],
                'APP_DIRS': ...,
                'OPTIONS': {...}
                ],
                'libraries': {
                    'common_tags': 'appname.templatetags.common_tags',
                    }
                },
            },
        ]

       

Repeat content by number of times:

    {% multiply <num: int> %}  
        [Content] 
    {% endmultiply %}


"range" it is generated list from range and passed to template tag "cycle" and might be used like "cycle" tag with number list, or in multiply like cycle number generator.  
Examples syntax:

    {% range <end: int> %}
    {% range <start: int> <end: int> %}
    {% range <start: int> <end: int> <step: int> %}
    {% range <start: int> <end: int> <step: int> as foo %}
    {% range <start: int> <end: int> <step: int> as foo [silent] %}
  
