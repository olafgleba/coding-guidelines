# Coding Guidelines #

**TOC**:

1. [Allgemeine Prinzipien](#allgemeine-prinzipien)
2. [Editoreinstellungen](#editoreinstellungen)
3. [Kommentare - CSS/SCSS](#kommentare-scss)
4. [Format - CSS/SCSS](#format-cssscss)
5. [Format - SCSS](#format-scss)

---


<a name="allgemeine-prinzipien"></a>
## 1. Allgemeine Prinzipien ##

+ Alle Regeln und Vorgaben dieses Guides sind verbindlich für alle  beteiligten Entwickler.
+ Ist nicht eindeutig, wie etwas zu deklarieren ist, sollte Rücksprache mit den Teammitgliedern gehalten bevor die Deklaration erfolgt.


<a name="editoreinstellungen"></a>
## 2. Editoreinstellungen ##

Grundsätzliche Einstellungen:

+ Für Einrückungen werden (Hard) **Tabs** genutzt.
+ Die Zeichenweite der Tabs ist auf **4** gesetzt.
+ Vermische *niemals* Leerzeichen mit Tabs.
+ Die maximale Zeilenlänge wird auf **80** Zeichen festgelegt.
+ Deklarationen, die mehr Zeichen in einer Zeile beinhalten, werden *nicht* per Hand umgebrochen.

### EditorConfig ###

Um den Code-Stil konsistent zu halten wird eine Datei genutzt, die Voreinstellungen für Texteditoren bereitstellt (`.editorconfig`). Dies gewährleistet, dass alle Teammitglieder mit einer identischen Konfiguration arbeiten und die Ansicht des Codes konsistent in allen Texteditoren bleibt. Damit der jeweilige Texteditor die Konfigurationsdatei interpretieren kann, müssen alle Teammitglieder ein entsprechendes Plugin installieren ([EditorConfig Plugin Downloads](http://editorconfig.org/#download)).


<a name="kommentare-scss"></a>
## 3. Kommentare - CSS/SCSS ##

Gut dokumentierter Code ist extrem wichtig. Beschreibe so ausführlich wie notwendig deinen Code, so dass andere verstehen können, was der Code kann und was ggf. nicht.

Grundsätzliche Regeln:

+ Kommentare werden auf **English** verfasst.
+ Kommentare werden in ganzen, beschreibenden Sätzen und korrekter Interpunktion verfasst.
+ Kommentare werden *immer* oberhalb des dokumentierten Codes plaziert
+ Zwischen Kommentar und dokumentierten Code wird **1** Leerzeile gesetzt.
+ Zwischen Code und einem nachfolgenden/nächsten Kommentar werden **2** Leerzeilen gesetzt.

### Arten von Kommentaren ###

Das Format von Kommentaren richtet sich danach, ob der kommentierte Code **allein der Inline Dokumentation** dient oder für die **Dokumentation im Living Style Guide** relevant ist.

### Kommentare für Inline Code Dokumentation ###

Kommentare werden im [JavaDoc](https://de.wikipedia.org/wiki/Javadoc) Format notiert.

Beispiel eines ausführlichen Kommentars:

```css
/**
 * Einzeilige Kurzbeschreibung
 * 
 * Ausführliche Beschreibung, die detailiert die Aufgabe des Codes
 * erklärt. Links und Beispiel Markup sind oft hilfreich oder gar
 * notwendig. Variablen oder/und Klassennamen werden mit Backticks
 * versehen (Bsp. `.example`).
 *
 * Example HTML:
 *
 * <ul class="example">
 * 		<li></li>
 *      ...
 * </ul>
 */
```

Ist es sinnvoll/notwendig einzelne Deklarationen zu erklären, werden sie wie im nachfolgenden Beispiel kommentiert.

```css
/**
 * Einzeilige Kurzbeschreibung
 * 
 * Ausführliche Beschreibung, die detailiert die Aufgabe des Codes
 * erklärt. Links und Beispiel Markup sind oft hilfreich oder gar
 * notwendig. Variablen oder/und Klassennamen werden mit Backticks
 * versehen (Bsp. `.example`).
 *
 * Example HTML:
 *
 * <ul class="example">
 *      <li></li>
 *      ...
 * </ul>
 *
 * 1. Remove list style and padding/margin
 * 2. Reset font size inherited from `.example`
 */

.example {
    list-style: none;
    padding: 0; /* 1 */
    margin: 0; /* 1 */

    li {
        font-size: 1 rem; /* 2 */
    }
}
```

Beispiel eines einfachen Kommentars:

```css
/* Einzeilige Kurzbeschreibung */
```


### Kommentare für die Dokumentation im Living Style Guide ###

Die Dokumentation von Sourcecode, der im Living Style Guide abgebildet werden soll, folgt etwas anderen Regeln. Der Living Style Guide wird mit dem Gem Hologram erstellt, dass bestimmte Konventionen in der Kommentierung erfordert.

*in Arbeit...*


<a name="format-cssscss"></a>
## 4. Format - CSS/SCSS ##

Grundsätzliche Regeln:

+ Eine öffnende geschweifte Klammer wird in der gleichen Zeile wie der Selektor notiert.
+ Setze einen einfachen Leerschritt zwischen Deklaration und öffenden geschweiften Klammer.
+ Eine schließende geschweifte Klammer einer Deklaration steht in eigener Zeile und gleichen Spalte wie der öffenende Selektor. 
+ Jeder Selektor in Selektorketten wird jeder Selektor in einer eigenen Zeile notiert.
+ Jede Deklaration wird mit einem Semikolon abgeschlossen.
+ Setze zwischen Attribut und Wert einer Deklaration ein Leerzeichen (e.g. `margin: 1em`).
+ Nutze ausschließlich HEX Angaben in Farbdeklarationen in der keine Transparenz erforderlich ist.
+ Nutze ausschließlich das RGBA Farbmodell, wenn Transparenzen erforderlich sind. 
+ Nutze durchgehend Kleinschreibung und Shorthand Schreibweise bei HEX Angaben (e.g. `#fff`).
+ Es werden ausschließlich doppelte Anführungzeichen genutzt.
+ Attributewerte werden in Anführungszeichen gesetzt (e.g. `input[type="text")`).
+ Nullwerte werden, soweit valide, ohne Maßeinheiten notiert (e.g. `margin: 0`)
+ Nach Kommata, die Werte/Eigenschaften separieren, wird ein jeweils ein Leerzeichen gesetzt (e.g. `font-family: helvetica, arial, sans-serif`).
+ Jeder Deklarationsblock wird durch **1** Leerzeile abgesetzt.

Beispiel der oben genannten Regeln:

```css
.selektor-1,
.selektor-2 {
    display: block;
    margin: 0; 
    color: #fff;
    background-color: rgba(0, 0, 0, 0.5);
}

input[type="text"] {
    font-family: helvetica, arial, sans-serif;
    font-size: inherit;
}
```

Ausnahmen:

+ Besteht die Deklaration aus lediglich eines Attribut/Werte-Paars, werden Selektor, geschweifte Klammer und die Attribut/Werte Deklaration in **1** Zeile notiert. Geschweifte Klammern und Deklaration werden durch einen Leerschritt voneinander abgesetzt.

Beispiel der oben genannten Regeln:

```css
.selektor { text-align: right; }
```



### Reihenfolge der Deklarationen

Deklarationen werden in Blöcken zusammenhängender Eigenschaften notiert. 

+ Jeder Eigenschaftsblock wird durch eine Leerzeile voneinander abgesetzt. 
+ Innerhalb der Eigenschaftblöcke folgt die Sortierung keiner stringenten Konvention, sondern orientiert sich nach sinnvoll gruppierbaren Eigenschaften (e.g. `top: 0; left: 0;` oder `width: 1em; height: 1em` etc.).
+ Zwischen den einzelnen Eigenschaftsblöcken wird **1** Leerzeile gesetzt.

```css
.selektor {
    /* Positionierung */
    position: relative;
    z-index: 1;
    top: 0;
    right: 0;

    /* Box Model */
    display: block;
    box-sizing: border-box;
    padding: 1em;
    margin: 1em;
    width: 10em;
    height: 10em; /* Zu vermeiden ;-) */
    overflow: hidden; 

    /* Sonstige Angaben */
    color: #fff;
    background-color: #000;
    font-family: helvetica, arial, sans-serif;
    font-size: inherit;
    text-align: left; 
}
```



<a name="format-scss"></a>
## 5. Format - SCSS ##

in Arbeit...




