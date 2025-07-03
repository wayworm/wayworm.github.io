---
category: meta
tags: [bugfix, Jekyll, liquid, troubleshooting, search]
math: true
---

### **Solution** :  

Change
```html {% raw %}
{{- description | strip | truncate: max_length | escape -}}{% endraw %}
```

To:
```html{%raw %}
  {{- description | strip | truncate: max_length
                | replace: '\', '\\\\'
                | replace: '"', '\"' -}} {% endraw %}
  ```

in ```post-description.html```

<br>
<br>
<br>

### Overview
I noticed the search feature on this blog wasn't working, so I fixed it. I assumed the issue was going to be with how 
the page was build, like a dependency issue.

It turns out that the json files being generated to be presented in the search results were not escaped properly when the liquid template passed in data. I spent a lot of time thinking it would be other issues, I hope you didn't have to. **Always check the console...**


### post-description.html
In ``` /_includes/post-description.html ``` we have:

```html{% raw %}
  {%- comment -%}
    Get post description or generate it from the post content.
  {%- endcomment -%}

  {%- assign max_length = include.max_length | default: 200 -%}

  {%- capture description -%}
  {%- if post.description -%}
    {{- post.description -}}
  {%- else -%}
    {% comment %}
      Remove the line number of the code snippet.
    {% endcomment %}
    {% assign content = post.content %}

    {% if content contains '<td class="rouge-gutter gl"><pre class="lineno">' %}
      {% assign content = content | replace: '<td class="rouge-gutter gl"><pre class="lineno">', '<!-- <td class="rouge-gutter gl"><pre class="lineno">'%}
      {% assign content = content | replace: '</td><td class="rouge-code">', '</td> --><td class="rouge-code">' %}
    {% endif %}

    {{- content | markdownify | strip_html | newline_to_br | replace: '<br />', ' ' | strip_newlines -}}
  {%- endif -%}
  {%- endcapture -%}

  {{- description | strip | truncate: max_length | escape -}}
  {% endraw %}
  ```

You only need to alter the final line so that the description varible has it's characters escaped if necessary. Replace it with:

``` html{% raw %}

{%- comment -%}
    Get post description or generate it from the post content.
  {%- endcomment -%}

  {%- assign max_length = include.max_length | default: 200 -%}

  {%- capture description -%}
  {%- if post.description -%}
    {{- post.description -}}
  {%- else -%}
    {% comment %}
      Remove the line number of the code snippet.
    {% endcomment %}
    {% assign content = post.content %}

    {% if content contains '<td class="rouge-gutter gl"><pre class="lineno">' %}
      {% assign content = content | replace: '<td class="rouge-gutter gl"><pre class="lineno">', '<!-- <td class="rouge-gutter gl"><pre class="lineno">'%}
      {% assign content = content | replace: '</td><td class="rouge-code">', '</td> --><td class="rouge-code">' %}
    {% endif %}

    {{- content | markdownify | strip_html | newline_to_br | replace: '<br />', ' ' | strip_newlines -}}
  {%- endif -%}
  {%- endcapture -%}

  {{- description | strip | truncate: max_length
                | replace: '\', '\\\\'
                | replace: '"', '\"' -}}
  {% endraw %}
```