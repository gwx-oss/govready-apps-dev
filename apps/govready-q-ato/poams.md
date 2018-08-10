id: poams
format: markdown
title: Plan of Action and Milestones
...
# User-Entered POAMs

{% for poam in project.poams %}
{{poam.output_documents.complete_text}}
{% endfor %}

# POAMs from Components

{% for question, answer in project.questions %}
  {% if "protocol" in question and "govready.com/apps/compliance/2017/nist-sp-800-171-r1-ssp" in question.protocol and answer %}
    {% if 'ssp_nist800171r1_poams' in answer.output_documents %}
## {{answer}}

{{answer.output_documents.ssp_nist800171r1_poams|safe}}
    {% endif %}
  {% endif %}
{% endfor %}