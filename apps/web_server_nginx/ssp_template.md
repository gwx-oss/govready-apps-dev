id: ssp_template
format: markdown
...
{% if not system_details.hostname %}
  The system will use an Nginx web server.
{% else %}
  The system has an Nginx web server at {{system_details.hostname}}.
{% endif %}
