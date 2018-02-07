================
    Jinja2
================


tojson() 
--------
This function converts the given object into JSON representation.
This is for example very helpful if you try to generate JavaScript on the fly.
Note that inside script tags no escaping must take place, 
so make sure to disable escaping with ``|safe`` before Flask 0.10 if you intend to use it inside script tags:
::

    <script type=text/javascript>
        doSomethingWith({{ user.username|tojson|safe }});
    </script>


filter
-------

::

    "datacenters": [{
        "description": "Main Datacenter", 
        "name": "main"
    }, {
        "description": "Secondaty Datacenter", 
        "name": "secondary"
    }]


sol::

    {{ (datacenters | selectattr("name", "equalto", "main") | list | first).description }}


set variable
----------------
::

    {% set navigation = [('index.html', 'Index'), ('about.html', 'About')] %}
