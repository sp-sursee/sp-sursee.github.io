---
layout: default
---

<script src="/assets/scripts/FileSaver.js"></script>
<script src="/assets/scripts/ics.js"></script>
<script>
function downloadIcs(subject, description, location, begin, end) {
    var cal = ics();
    cal.addEvent(subject, description, location, begin, end);
    cal.download(subject);
}
</script>

## Termine

{% include event.html title="Parteiversammlung" date="2024-11-1" begin="19:30" end="23:00" location="Craftwerk Sursee" %}
{% include event.html title="Parteiversammlung" date="2024-11-1" begin="19:30" end="23:00" location="Craftwerk Sursee" %}
{% include event.html title="Parteiversammlung" date="2024-11-1" begin="19:30" end="23:00" location="Craftwerk Sursee" %}
{% include event.html title="Parteiversammlung" date="2024-11-1" begin="19:30" end="23:00" location="Craftwerk Sursee" %}

