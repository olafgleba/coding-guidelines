# Coding Guidelines #

**TOC**:

1. [Prämissen](#praemisse)
2. [Editoreinstellungen](#editoreinstellungen)
3. [Kommentare](#kommentare)
    - [CSS](#kommentare-css)
    - [HTML/Markup](#kommentare-markup)
4. [Format](#format)
    - [CSS](#format-css)
    - [HTML/Markup](#format-markup)

---


<a name="praemisse"></a>
## 1. Prämissen ##

+ Alle Regeln und Vorgaben dieses Guides sind verbindlich für alle  beteiligten Entwickler.
+ Ist nicht eindeutig, wie etwas zu deklarieren ist, wird Rücksprache mit den Teammitgliedern gehalten.


<a name="editoreinstellungen"></a>
## 2. Editoreinstellungen ##

Die (meisten) Einstellungen gelten übergreifend für CSS wie auch HTML/Markup.

Grundsätzliche Einstellungen/Regeln:

+ Für Zeileneinzüge werden **Spaces** genutzt.
+ Die Einrückungsweite wird auf **4** gesetzt.
+ Vermische *niemals* Leerzeichen mit Tabs. 
+ Die maximale Zeilenlänge wird auf **80** Zeichen begrenzt (*nur CSS*).
+ Deklarationen, die mehr Zeichen in einer Zeile beinhalten, werden *niemals* per Hand umgebrochen.

### EditorConfig ###

Um den Code-Stil konsistent zu halten wird eine Datei genutzt, die Voreinstellungen für Texteditoren bereitstellt (`.editorconfig`). Dies gewährleistet, dass alle Teammitglieder mit einer identischen Konfiguration arbeiten und die Ansicht des Codes konsistent in allen Texteditoren bleibt. Damit der jeweilige Texteditor die Konfigurationsdatei interpretieren kann, müssen alle Teammitglieder ein entsprechendes Plugin installieren ([EditorConfig Plugin Downloads](http://editorconfig.org/#download)).


<a name="kommentare"></a>
## 3. Kommentare ##

Gut dokumentierter Code ist extrem wichtig. Beschreibe so ausführlich wie notwendig deinen Code, so dass andere verstehen können, was der Code kann und was ggf. nicht.

Grundsätzliche Regeln:

+ Kommentare werden auf **English** verfasst.
+ Kommentare werden in ganzen, beschreibenden Sätzen und korrekter Interpunktion verfasst.
+ Kommentare werden *immer* oberhalb des dokumentierten Codes/Markup plaziert
+ Zwischen Kommentar und dokumentierten Code/Markup wird **1** Leerzeile gesetzt.
+ Ganze Kommentar/Code Blocks werden durch **2** Leerzeilen voneinander abgesetzt.

<a name="kommentare-css"></a>
### CSS ###

Das Format von Kommentare richtet sich danach, ob der kommentierte Code **allein der Inline Dokumentation** dient oder für die **Dokumentation im Living Style Guide** relevant ist.

#### Kommentare für Inline Code Dokumentation ####

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
        font-size: 1rem; /* 2 */
    }
}
```

Oftmals ist eine ausführliche Kemmentierung einer Deklaration nicht notwendig, sondern verdeutlich nur den Kontext des Codes. In dem Fall wird ein einzeiliger Kommentar verwendet.

Beispiel eines einfachen Kommentars:

```css
/* Status Klasse für Slider  */

.slider.is-hidden { 
	display: none;
}
```


#### Kommentare für die Dokumentation im Living Style Guide ####

Die Dokumentation von Sourcecode, der im Living Style Guide abgebildet werden soll, folgt etwas anderen Regeln. Der Living Style Guide wird mit dem Gem Hologram erstellt, dass bestimmte Konventionen in der Kommentierung erfordert.

*in Arbeit...*


<a name="kommentare-markup"></a>
### HTML/Markup ###

Kommentare im Markup sollten generell sparsam verwendet werden, da diese nicht entfernt werden im Deployment und durch korrekte Editoreinstellung (Einzug) i.d.R. schnell erkannt werden kann, wo ein Element beginnt und wo es endet. Für das visuelle Erfassen von Zusammenhängen ist es dennoch sinnvoll, das Ende eines größeren Markup-Blocks durch einen Kommentar auszuzeichnen.

+ Ein Kommentar beginnt mit einem Schrägstrich (Synomym für das Ende eines Blocks).
+ Ist keine Klassendeklaration vorhanden, wird der Tag-Name notiert.
+ Hat das Element einen Klassennamen, wird dieser notiert.

```html
<header>
    ...
</header> <!-- /header -->


<header class="banner">
    ...
</header> <!-- /.banner -->
```



<a name="format"></a>
## 4. Format ##

<a name="format-css"></a>
### CSS ###

Grundsätzliche Regeln:

+ Eine öffnende geschweifte Klammer wird in der gleichen Zeile wie der selector notiert.
+ Setze einen einfachen Leerschritt zwischen Deklaration und öffenden geschweiften Klammer.
+ Eine schließende geschweifte Klammer einer Deklaration steht in eigener Zeile und gleichen Spalte wie der öffenende selector. 
+ Jeder selector in selectorketten wird in einer eigenen Zeile notiert.
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
.selector-1,
.selector-2 {
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

##### Ausnahme: ######

+ Besteht die Deklaration aus lediglich eines Attribut/Werte-Paars **und** ist Teil einer zusammenhängenden Gruppe von Deklarationen, werden selector, geschweifte Klammer und die Attribut/Werte Deklaration jeweils in **1** Zeile notiert. Geschweifte Klammern und Deklaration werden durch einen Leerschritt voneinander abgesetzt.

Beispiel der oben genannten Regeln:

```css
.u-text-align--left { text-align: left; }
.u-text-align--right { text-align: right; }
.u-text-align--center { text-align: center; }
```


#### Reihenfolge der Deklarationen ####

Deklarationen werden in Blöcken zusammenhängender Eigenschaften notiert. 

+ Jeder Eigenschaftsblock wird durch eine Leerzeile voneinander abgesetzt. 
+ Innerhalb der Eigenschaftblöcke folgt die Sortierung keiner stringenten Konvention, sondern orientiert sich nach sinnvoll gruppierbaren Eigenschaften (e.g. `top: 0; left: 0;` oder `width: 1em; height: 1em` etc.).
+ Zwischen den einzelnen Eigenschaftsblöcken wird **1** Leerzeile gesetzt.

```css
.selector {
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



#### Präprozessoren ####

Der Einsatz von (hier) SASS erfordert einige weitere Regeln, die verbindlich sind.  

+ Vermeide Verschachtelungen wo immer es möglich ist.
+ Verschachtelung (Nesting) wird auf max. **2** Ebenen begrenzt.
+ Verschachtelte Deklaration werden vor und nach der Notation durch **1** Leerzeile von dem umgebenden Code abgesetzt.
```scss
.selector {
    color: red;

    .selector-nested {
        ...
    }
    
}
```

+ `@extend`, `@include` werden am Anfang einer Deklaration notiert (in dieser Reihenfolge.
+ Notierungen von SASS eigenen Statements (`@`) werden mit **1** Leerzeile von nachfolgenden Deklarationen abgesetzt. 
+ Um Konflikte mit ggf. Dritt-Libraries zu vermeiden, werden eigene Mixins und Funktionen mit einem Namespace-Prefix deklariert (Wahl des Prefix projektabhängig; im Beispiel wird `x-` als Prefix genutzt).

```scss
.selector {
    @extend %button;
    @include font-size(16px);

    width: x-calculate-context(64em);
    ...
}
```


<a name="format-markup"></a>
### HTML/Markup ###

Ein paar wenige Regeln gibt es auch für die Notation von Klassen innerhalb des Markups und Abständen zwischen Markup-Blöcken.

+ Der schließende Tag eines HTML-Elementes wird in der gleichen Zeile wie der öffnende Tag notiert.
+ Nach dem öffnenden Tag eines HTML-Elementes werden die Inhalte i.d.R. in einer neuen Zeile begonnen. Ausnahmen sind Elemente, die keine weiteren Elemente enthalten (bspw. `<a>`).
+ Attribute im Markup werden immer in doppelte Anführungszeichen gesetzt.
```html
<div class="c-vehicle-list">
    <ul>
        <li>
            <a>...</a>
        </li>
    </ul>
</div>


<dl>
    <dt>Term</dt>
    <dd>Description</dd>

    <dt>Term</dt>
    <dd>
        <span>Description</span>
    </dd>
</dl>
```

+ Bei Mehrfachzuweisungen von Klassen-Attributen, werden diese mit jeweils **2** Leerschritten voneinander abgesetzt. Dies ist sinnvoll, da ab einer bestimmten Zahl an Attributen die Übersichtlichkeit verloren geht.
```html
<div class="btn  btn--small  btn--submit">
```

+ Layoutrelevante Markup-Blöcke werden durch **3** Leerzeilen voneinander abgesetzt.
```html
<header>
    ...
</header>


<main>
    ...


    <aside>
        ...
    </aside>
</main>


<footer>
    ...
</footer>
```



