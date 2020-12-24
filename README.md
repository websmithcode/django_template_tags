# django_template_tags
Custom template tags for django.

> Adds tags such, as: "multiply", "range", "or"   
> Before use needs load {% load common_tags %}

# For install:  
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

## Multiply
Repeat content by number of times:

    {% multiply <num: int> %}  
        [Content] 
    {% endmultiply %}

## Range
"range" it is generated list from range and passed to template tag "cycle" and might be used like "cycle" tag with number list, or in multiply like cycle number generator.  
Examples syntax:

    {% range <end: int> %}
    {% range <start: int> <end: int> %}
    {% range <start: int> <end: int> <step: int> %}
    {% range <start: int> <end: int> <step: int> as <var> %}
    {% range <start: int> <end: int> <step: int> as <var> [silent] %}
    
## Or
"or" it is simplified recording of the tag "if"-"else"

old recording:
    
    {% if value_0 %}
        {{ value_0 }}
    {% else %}
        {% if value_1 %}
            Content string
        {% else %}
            {{ value_2 }}
        {% endif %}
    {% endif %}

new recording:

    {% or value_0 "Content string" value_2 %}
