{% set is_open_source = cookiecutter.open_source_license != 'Not open source' -%}
{% for _ in cookiecutter.project_name %}={% endfor %}
{{ cookiecutter.project_name }}
{% for _ in cookiecutter.project_name %}={% endfor %}

{% if is_open_source %}
.. image:: https://img.shields.io/pypi/v/{{ cookiecutter.github_repo }}.svg
        :target: https://pypi.python.org/pypi/{{ cookiecutter.github_repo }}

.. image:: https://img.shields.io/travis/{{ cookiecutter.github_username }}/{{ cookiecutter.github_repo }}.svg?branch=master
        :target: https://travis-ci.org/{{ cookiecutter.github_username }}/{{ cookiecutter.github_repo }}?branch=master

.. image:: https://readthedocs.org/projects/{{ cookiecutter.github_repo | replace("_", "-") }}/badge/?version=stable
        :target: https://{{ cookiecutter.github_repo | replace("_", "-") }}.readthedocs.io/en/stable/?badge=stable
        :alt: Documentation Status
{%- endif %}

{% if cookiecutter.add_pyup_badge == 'y' %}
.. image:: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/shield.svg
     :target: https://pyup.io/repos/github/{{ cookiecutter.github_username }}/{{ cookiecutter.project_slug }}/
     :alt: Updates
{% endif %}

{{ cookiecutter.project_short_description }}

{% if is_open_source %}
* Free software: {{ cookiecutter.open_source_license }}
* Documentation: https://{{ cookiecutter.github_repo | replace("_", "-") }}.readthedocs.io.
* Python versions: Python {% if cookiecutter.use_python2 == "y" %}2.7, {% endif %}3.5, 3.6
{% endif %}
