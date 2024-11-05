# Grundlagen des Semantischen HTML
https://ehy-classroom.github.io/semantic-html-basics/

HTML5 bietet eine Reihe von semantischen Tags, die den Inhalt und die Struktur einer Webseite besser beschreiben. Im Gegensatz zu generischen Tags wie `<div>` oder `<span>` tragen semantische Tags wie `<header>`, `<main>`, `<section>` oder `<article>` dazu bei, den Zweck und die Bedeutung von Inhalten klar zu machen. Dies verbessert die Zugänglichkeit für Screenreader, die Suchmaschinenoptimierung (SEO) und die allgemeine Strukturierung der Seite.

Diese semantischen Tags sind darauf ausgelegt, typische Inhaltsbereiche wie Kopfzeilen, Hauptinhalte, Navigationsleisten und Artikel logisch abzugrenzen. So können Benutzer und Suchmaschinen verstehen, wie der Inhalt strukturiert ist und wo wichtige Informationen zu finden sind. Sie helfen auch, den Quellcode übersichtlicher zu gestalten und vereinfachen die Zusammenarbeit in der Webentwicklung, da der Code lesbarer und selbstbeschreibend wird.



## Hier sind die wichtigsten semantischen HTML-Elemente und ihre Verwendung:

**`<header>`**
Markiert den Kopfbereich eines Dokuments oder eines Inhaltsabschnitts. Es wird für allgemeine Informationen wie Seitentitel, Logos oder Navigation verwendet und kann in verschiedenen Abschnitten (z. B. `article` oder `section`) vorkommen.

**`<footer>`**
Kennzeichnet den Fußbereich eines Dokuments oder Abschnitts und enthält oft Copyright-Informationen, Links oder Autorenangaben. Wie `<header>` kann es in mehreren Abschnitten verwendet werden.

**`<main>`**
Definiert den Hauptinhalt der Seite, der sich auf den zentralen Zweck bezieht. Dieser Bereich sollte nur einmal pro Seite vorkommen und nicht innerhalb von `article`, `section` oder anderen Container-Elementen stehen.

**`<article>`**
Stellt einen eigenständigen Inhalt dar, der auch außerhalb des Kontexts der Seite sinnvoll ist. Ein Blogbeitrag, ein Zeitungsartikel oder ein Forumspost sind typische Beispiele.

**`<section>`**
Dient zur thematischen Gliederung eines Inhaltsbereichs. Ein `section`-Element gruppiert verwandte Inhalte und sollte eine eigene Überschrift haben, um den Bereich klar abzugrenzen.

**`<nav>`**
Kennzeichnet Navigationslinks, die zur Orientierung auf der Seite oder innerhalb des Dokuments dienen, z. B. Hauptmenüs oder Seitennavigationen.

**`<aside>`**
Definiert Inhalte, die zum Hauptinhalt ergänzt sind, aber nicht direkt zum Thema gehören. Beispiele sind Sidebar-Inhalte, Werbung oder zusätzliche Links.

<figure> Dient zur Einbettung eigenständiger Medieninhalte, z. B. Bilder oder Diagramme, die mit dem Hauptinhalt verbunden sind. Es wird oft mit einer Bildunterschrift im <figcaption>-Element verwendet.

**`<figcaption>`**
Verwendet für die Beschreibung eines `<figure>`-Elements. Es enthält eine Bildunterschrift oder zusätzliche Informationen zum Medieninhalt.

**`<address>`**
Gibt Kontaktinformationen oder Autorendetails an. Dieses Element kann für Adressen und Kontaktinformationen verwendet werden und ist meist im `footer` eines `article`-Elements sinnvoll.

**`<h1>–<h6>`**
Überschriftenelemente, die die Hierarchie des Inhalts definieren und die Struktur der Seite klar erkennbar machen. `<h1>` steht für die Hauptüberschrift der Seite, während `<h2>–<h6>` Unterüberschriften in absteigender Reihenfolge darstellen.

**`<time>`**
Verwendet zur Darstellung von Datum und Uhrzeit und erleichtert die maschinelle Lesbarkeit dieser Informationen. Dies ist nützlich für Veröffentlichungsdaten oder Zeitangaben in einem Artikel.

---

## ARIA

ARIA (Accessible Rich Internet Applications) ist ein Satz von Attributen, der dabei hilft, Webseiten und Webanwendungen für Menschen, die Screenreader oder andere Hilfsmittel verwenden, zugänglicher zu machen. Mit ARIA kann man interaktive Elemente und Inhalte klar beschreiben, damit assistive Technologien wissen, was sie den Nutzern „sagen“ oder wie sie sich verhalten sollen. Das ist besonders wichtig, wenn HTML allein nicht ausreicht, um die Funktion oder den Zweck eines Elements klarzumachen.

### Hier sind die wichtigsten ARIA-Attribute und wie sie genutzt werden:

**`role`**  
Das `role`-Attribut beschreibt die Funktion eines Elements. Es gibt an, was ein Element ist oder wie es sich verhalten soll.

Beispiele:
```html
<div role="button">Klick mich</div> <!-- wird als Schaltfläche behandelt -->
<nav role="navigation"> <!-- wird als Navigationsbereich erkannt -->
```

**`aria-label`**  
Gibt einem Element einen eindeutigen Namen, damit Screenreader den Zweck des Elements besser erklären können. Nützlich, wenn das Element selbst keinen sichtbaren Text enthält.

Beispiel:
```html
<button aria-label="Suche öffnen">🔍</button> <!-- beschreibt das Symbol als Suchschaltfläche -->
```

**`aria-labelledby`**  
Verweist auf ein anderes Element, das als beschreibender Text dient. Häufig genutzt für komplexere Beschreibungen.

Beispiel:
```html
<h2 id="dialogTitle">Dialogfenster</h2>
<div role="dialog" aria-labelledby="dialogTitle">
    <!-- Der Screenreader sagt: „Dialogfenster“ -->
</div>
```

**`aria-describedby`**  
Verweist auf ein Element, das zusätzliche Informationen gibt. Dies ist nützlich für Beschreibungen oder Anweisungen, die bei Bedarf vorgelesen werden sollen.

Beispiel:
```html
<input aria-describedby="passwordHint" type="password">
<span id="passwordHint">Mindestens 8 Zeichen</span>
```

**`aria-hidden`**  
Sagt Screenreadern, ob sie ein Element ignorieren sollen (`aria-hidden="true"`), z. B. bei dekorativen Bildern oder überflüssigen Informationen.

Beispiel:
```html
<img src="decorative.png" aria-hidden="true" alt="">
```

**`aria-live`**  
Für dynamische Inhalte, die sich ohne Seitenaktualisierung ändern (z. B. Nachrichten oder Ladeanzeigen). `aria-live="polite"` wartet, bis der Nutzer bereit ist, `aria-live="assertive"` liest sofort.

Beispiel:
```html
<div aria-live="polite">Neue Nachricht erhalten...</div>
```

**Zusammengefasst**:  
ARIA-Attribute verbessern die Zugänglichkeit und helfen, die Funktion und Bedeutung von Elementen klar darzustellen, besonders bei dynamischen und interaktiven Webseiten.

### ARIA-Rollen

Hauptsächlich sind die **ARIA-Rollen** für die Semantik relevant, weil sie die Funktion und Bedeutung eines Elements innerhalb der Seite definieren. Rollen wie `button`, `navigation`, `main` oder `alert` sagen assistiven Technologien, *was* ein Element ist und *welche Funktion* es erfüllt – das ist der Kern der Semantik in ARIA.

Andere ARIA-Attribute wie `aria-label`, `aria-labelledby`, `aria-describedby`, `aria-live` und `aria-hidden` sind **ergänzende Attribute**. Diese Attribute haben weniger mit Semantik zu tun, sondern vielmehr damit, wie Inhalte für Benutzer präsentiert und zugänglich gemacht werden. Sie geben zusätzliche Hinweise oder steuern, wie assistive Technologien mit Inhalten umgehen, besonders bei dynamischen Inhalten oder interaktiven Elementen.

**Zusammengefasst**: Die ARIA-Rollen sind die primären semantischen Elemente, weil sie die Struktur und Bedeutung eines Elements angeben. Andere ARIA-Attribute ergänzen die Benutzerfreundlichkeit und Zugänglichkeit, beeinflussen jedoch die Semantik weniger direkt.



### Hier sind die wichtigsten ARIA-Rollen, jede mit einem Codebeispiel:

**`role="banner"`**  
Kennzeichnet den Haupt-Header der Seite, sollte nur einmal pro Seite verwendet werden.

```html
<header role="banner">
    <h1>Website Title</h1>
    <nav>
        <a href="#home">Home</a>
        <a href="#about">About</a>
    </nav>
</header>
```

**`role="navigation"`**  
Markiert Navigationsbereiche wie Menüs.

```html
<nav role="navigation">
    <ul>
        <li><a href="#section1">Section 1</a></li>
        <li><a href="#section2">Section 2</a></li>
    </ul>
</nav>
```

**`role="main"`**  
Definiert den Hauptinhalt der Seite, darf nur einmal pro Seite verwendet werden.

```html
<main role="main">
    <article>
        <h2>Main Content Title</h2>
        <p>This is the primary content of the page.</p>
    </article>
</main>
```

**`role="complementary"`**  
Wird für Inhalte verwendet, die den Hauptinhalt ergänzen, z. B. eine Sidebar.

```html
<aside role="complementary">
    <h3>Related Links</h3>
    <ul>
        <li><a href="#link1">Related Link 1</a></li>
        <li><a href="#link2">Related Link 2</a></li>
    </ul>
</aside>
```

**`role="contentinfo"`**  
Kennzeichnet den Haupt-Footer der Seite und sollte ebenfalls nur einmal pro Seite verwendet werden.

```html
<footer role="contentinfo">
    <p>&copy; 2024 Your Company</p>
    <a href="#privacy">Privacy Policy</a>
</footer>
```

**`role="button"`**  
Ermöglicht es, ein nicht-button-Element wie eine Schaltfläche wirken zu lassen.

```html
<div role="button" tabindex="0" onclick="alert('Button clicked!')">
    Click me
</div>
```

**`role="alert"`**  
Definiert eine Nachricht, die sofort vorgelesen wird, wenn sie in den DOM eingefügt wird, ideal für Fehlermeldungen.

```html
<div role="alert">
    Error: Something went wrong!
</div>
```

**`role="dialog"`**  
Markiert ein Dialogfenster oder Popup und wird häufig für Modals verwendet.

```html
<div role="dialog" aria-labelledby="dialogTitle">
    <h2 id="dialogTitle">Dialog Title</h2>
    <p>This is a dialog message.</p>
    <button onclick="closeDialog()">Close</button>
</div>
```

**`role="status"`**  
Informiert über Statusmeldungen, die weniger dringend als `role="alert"` sind, z. B. Ladefortschritte.

```html
<div role="status">
    Loading... Please wait.
</div>
```

**`role="progressbar"`**  
Wird für Fortschrittsbalken verwendet, z. B. bei Uploads oder Ladevorgängen.

```html
<div role="progressbar" aria-valuenow="60" aria-valuemin="0" aria-valuemax="100">
    60% complete
</div>
```

Diese ARIA-Rollen verbessern die Zugänglichkeit und Verständlichkeit von Webseiten besonders für Screenreader und assistive Technologien, indem sie Kontext und Interaktivität von Elementen klar kennzeichnen.

