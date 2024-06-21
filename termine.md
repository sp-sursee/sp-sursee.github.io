---
layout: default
---

<script src="/assets/scripts/FileSaver.js"></script>
<script src="/assets/scripts/ics.js"></script>
<script>
function toUTC(date_string) {
    let local_date = new Date(date_string);
    let utc_date = new Date(local_date.getTime() + local_date.getTimezoneOffset() * 60000);
    return utc_date;
}
function downloadIcs(subject, description, location, begin, end) {
    console.log(subject, description, location, begin, end);
    var cal = ics();
    cal.addEvent(subject, description, location, toUTC(begin), toUTC(end));
    console.log(cal.build());
    cal.download(subject);
}
</script>

## Termine

{% include event.html title="SP Politbier mit Kijan Espahangizi" date="2024-9-10" begin="19:30" end="23:00" location="Craftwerk Sursee" description="Historiker Kijan Espahangizi, Geschäftsführer des Zentrums Geschichte des Wissens (ZGW) der ETH & Universität Zürich referiert über Migration und Integration." %}

{% include event.html title="Kantonale und Nationale Abstimmungen" date="2024-9-22" %}

{% include event.html title="SP Themenabend voraussichtlich Thema Wasserqualität" date="2024-10-22" begin="19:30" end="23:00" location="Craftwerk Sursee" description="Gemeinsames Eintauchen und Diskutieren über die Themen (Trink-)Wasserqualität und Gewässerschutz." %}

{% include event.html title="Kantonale und Nationale Abstimmungen" date="2024-11-24" %}

{% include event.html title="SP Sursee Parteiversammlung" date="2024-11-26" begin="19:30" end="23:00" description="Traktanden sind unter anderem das Budget und die Rechnung der Stadt, sowie an der EGV traktandierte Geschäfte." %}

{% include event.html title="Ordentliche Einwohnergemeindeversammlung" date="2024-12-09" begin="19:30" end="23:00" location="Tuchlaube im Rathaus Sursee" %}

<script>
    let elements = document.getElementsByClassName("event");
    for (let i = 0; i < elements.length; i++) {
        let element = elements[i];
        let date_utc = toUTC(element.getAttribute("date"));
        let now = new Date();
        if (date_utc < now) {
            element.remove();
        }
    }
</script>