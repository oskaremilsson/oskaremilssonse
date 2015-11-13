---
layout: post
title:  "Reflektion"
date:   2015-11-10 19:06:28
---
- Vad är dina tankar om att pre-kompilera din CSS?
===
    - Jämför med vanlig CSS
    - Vilka tekniker använde du?
    - Fördelar och nackdelar?

    Jag gillar verkligen pre-compiling CSS! Det absolut bästa är att kunna nesta css-attribut, det blir så mycket lättare att både
skriva CSS-koden och att läsa den samma. Jag har använt nested css överallt där det passar och det är kommer bli roligare med
css-kodning i framtiden. Mixins finns även för mediaquerys för responsiviteten. Variabler används för alla färger och liknande.
När jag lade till knapparna för social media på startsidan så använde jag variabler för bredden då både ul och li-taggarna behövde få samma bredd.

    Fördelarna med att pre-kompilera css-kod är att det det blir smidigare för min som kodare att kunna dela upp i flera små filer och
använda nesting, variabler och mixins. Men det blir även snabbare för användaren att ladda in webbplatsen eftersom att
det bara blir en request för all css eftersom det lägger sig i en fil.

    Den enda nackdelen jag kan se är att det blir lite tyngre att rodda sidan och att man behöver ett system som klarar att kompilera sidan.
Man kan inte bara koda ihop lite lätt och sedan ladda upp det via en FTP-server.

- Vad är dina tankar om static site generators?
===
    - Vilken typ av projekt är det passande för?

    Static site generators är ett underbart sätt att tillhandahålla en statisk sida som inte ska uppdateras frekvent. Det är
snabbt att ladda eftersom allting är statiskt och packas ihop i filer som gör så få anrop till servern som möjligt.

    Det blir otroligt smidigt för mig som utvecklare att hantera en förändring eftersom det använder sig av layouts för html-strukturen
och pre-kompiling css gör det möjligt att tex använda sig av variabler i css-koden.


- Vad är robots.txt och hur har du konfigurerat den för din webbplats?
===
Robots-txt är en liten fil som sökmoterer och bottar hämtar för att ta reda på vilka mappar dom har åtkomst åt och inte.
Man kan styra fritt om man vill att tex enbart google ska få indexera mina filer, ingen alls eller någon speciell bot man själv kör.
På mina webbplats får dom gå igenom allting förutom att använda bilderna i bildsök på tex. google.

- Vad är humans.txt och hur har du konfigurerat den för din webbplats?
===
Humans-txt är en fil som finns lättillgängligt för oss människor att se vilka som ligger bakom en webbplats och kan tex innehålla
kontaktuppgifter och vilka programvaror som används vid utvecklingen.
På min webbplats finns det information om mitt namn, vart i världen jag bor och lite mjukvaror jag använt. Det finns även "thanks to".

- Hur implementerade du kommentarer till dina blogginlägg?
===
Jag använde mig av disqus som rekomenderades. Det var otroligt smidigt att registrera ett konto och hämta scriptet.
Scriptet valde jag att placera på layout-filen för en post. Jag försökte flytta ut scriptet till en fil istället men
fick då error ILLEGAL och fick det inte att rulla. På sidan som visar alla posts finns ett script som visar antalet kommentarer
på varje post. Det finns även ett litet "noscript" som visas om användaren har
javascript avstängt så man ser att det finns innehåll man inte kan se pga. de inställningarna.

{% highlight javascript %}
(function() {
var d = document, s = d.createElement('script');

s.src = '//example.disqus.com/embed.js';

s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
{% endhighlight %}

- Vad är Open Graph och hur får du ut något från det?
===
Open Graph är ett objekt man skapar i HTML-head som meddelar sidor som vill länka hur länken ska presenteras. Tex. när man
delar webbplatsen till facebook kan man styra titel, bild och en beskrivning. Det är otroligt kraftfullt att få till en snygg
 länk på facebook eftersom det kan resultera i flera klick och mer trafik till webbplatsen. Men det kan också göra att en
 webbplats kan luras med vad som förväntas finnas på hemsidan genom att lägga till en orelevant bild, tex för click-baits.
