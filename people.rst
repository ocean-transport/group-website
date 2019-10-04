Group Members
=============

.. jinja:: people

    {% for category, cat_people in people.items() %}

    {{ category | replace("_", " ") }}
    ----------------------------------

    {% for person in cat_people %}
    {{ person.name }}
    ~~~~~~~~~~~~~~~~~

    {% if person.email %}
    - **email**: {{ person.email }}
    {% endif %}
    {% if person.website %}
    - **website**: {{ person.website }}
    {% endif %}

    {% if person.orcid %}
    .. image:: https://img.shields.io/static/v1?label=ORCID&message={{ person.orcid }}&color=green&style=flat-square&logo=orcid
       :alt: ORCID Profile
       :target: https://orcid.org/{{ person.orcid }}
    {% endif %}

    {% if person.github %}
    .. image:: https://img.shields.io/github/followers/{{ person.github }}?label=Github&logo=github&style=flat-square
       :alt: GitHub Profile
       :target: http://github.com/{{ person.github }}
    {% endif %}

    {% if person.twitter %}
    .. image:: https://img.shields.io/twitter/follow/{{ person.twitter }}?logo=twitter&style=flat-square
        :alt: Twitter
        :target: https://twitter.com/{{ person.twitter }}
    {% endif %}

    {{ person.bio }}

    {% if person.pic %}
    .. image:: _static/photos/{{ person.pic }}
       :width: 200px
       :alt: {{ person.name }}

    {% endif %}

    {% endfor %}

    {% endfor %}
