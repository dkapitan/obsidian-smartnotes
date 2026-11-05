project::[[Getting Started]]
- [ ] #cont/in/read 

![[Pasted image 20250228064738.png]]
![[Pasted image 20250228064859.png]]

## File name
```
Rw. {{author}}. {{title}} ({{category}})
```

## Full Document Text file name
```
Rw-Fulltext. {{author}}. {{title}}
```

![[Pasted image 20250228065629.png]]
![[Pasted image 20250228065809.png]]
## Page Metadata

```
## Metadata
- Author: {% if author %}{{author}}{% endif %} ({{published_date}})
- Full Title: {{full_title}}
- Category:: {{category}}
{% if document_tags -%}
- Document Tags: {% for tag in document_tags %}[[{{tag}}]] {% endfor %}
{% endif -%}
{% if book_id-%}
{{book_id}}
{% endif -%}
{% if url -%}
- URL: {{url}}
{% endif -%}
- Citekey:: 

## Notes
{{document_note}}
```

## Highlights Header
```
{% if is_new_page %}
- [ ] ## Highlights
{% elif has_new_highlights -%}
- [ ] ## New highlights added {{date|date('F j, Y')}} at {{time}}
{% endif -%}
```

## Highlight
```
- {{ highlight_text }}{% if highlight_location and highlight_location_url %} ([{{highlight_location}}]({{highlight_location_url}})){% elif highlight_location %} ({{highlight_location}}){% endif %}{% if highlight_tags %}
- Tags: {% for tag in highlight_tags %}[[{{tag}}]] {% endfor %}{% endif %}{% if highlight_note %}

{{ highlight_note }}{% endif %}
```

## Full Document Text Link
```
## Full Document
[[{{ full_document_text_path }}|See full document content →]]
```
## Full Document Text
```
## Full Document
{{ full_text }}
```
![[Pasted image 20250228070745.png]]