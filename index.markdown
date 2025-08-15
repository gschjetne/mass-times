---
layout: page
---

{% for occasion in site.data.masses %}
{% assign priest = site.data.priests[occasion.priest] %}
{% assign location = site.data.locations[occasion.location] %}
{% assign month = occasion.time | date: "%m" %}

# {{ occasion.time | date: "%e" }} {% case month %}

{% when "01" %}Januari
{% when "02" %}Februari
{% when "03" %}Mars
{% when "04" %}April
{% when "05" %}Mai
{% when "06" %}Juni
{% when "07" %}Juli
{% when "08" %}Augusti
{% when "09" %}September
{% when "10" %}Oktober
{% when "11" %}November
{% when "12" %}December
{% endcase %}

{{ occasion.time | date: "%R" }} **{{ occasion.mass }}**

*{{ priest.name }}*

{{ location.name }}  
{{ location.street }}  
{{ location.postcode}} {{ location.town }}

{% endfor %}
