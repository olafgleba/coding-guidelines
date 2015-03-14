# Coding Guidelines #

---

**TOC**:

---

1. [**Grundsätze**](#markdown-header-allgemeine-prinzipien)
2. [**Editoreinstellungen**](#markdown-header-editoreinstellungen)
3. [**Kommentare**](#markdown-header-kommentare)

---

## 1. Allgemeine Prinzipien ##

+ Alle Regeln und Vorgaben dieses Guides sind verbindlich für alle  beteiligten Entwickler.
+ Code sollte so aussehen, als wenn ihn ein einzelner Entwickler geschrieben hat. Auch wenn ggf. viele daran mitgewirkt haben.
+ Falls ihr euch unsicher seid wie etwas zu machen ist oder eine noch hier noch nicht aufgeführtes Problem auftritt, sprecht die Kollegen an.

## 2. Editoreinstellungen ##

+ Für Einrückungen werden (echte) **Tabs** genutzt.
+ Die Zeichenweite der Tabs ist auf **4** gesetzt.
+ Vermische *niemals* einfache Leerzeichen mit Tabs.
+ Die maximale Zeilenlänge wird auf **80** Zeichen festgelegt.

Um den Code-Stil konsistent zu halten wird die Datei `.editorconfig` (versteckte Datei, liegt im [Root](https://bitbucket.org/autrado/autrado-frontend-development/src/)) von allen Teammitgliedern eingesetzt/genutzt. Diese enthält einige Voreinstellungen für Text-Editoren, so dass gewährleistet ist, dass alle Teammitglieder mit der gleichen Konfiguration arbeiten. Damit der Texteditor eurer Wahl die Datei (`.editorconfig`) versteht, müsst ihr für euren Texteditor ein Plugin installieren ([EditorConfig Plugin Downloads](http://editorconfig.org/#download)).

## 3. Kommentare ##

Gut dokumentierter Code ist extrem wichtig. Beschreibe so ausführlich wie notwendig deinen Code, so dass andere verstehen können, was der Code kann und was ggf. nicht.

Grundsätzliches zu Kommentaren:

+ Kommentare werden auf **English** verfasst.
+ Kommentare werden in ganzen, beschreibenden Sätzen und korrekter Interpunktion verfasst.

Die Art der Schreibweise von Kommentaren richtet sich danach, ob der kommentierte Code allein der Code-Beschreibung dient oder für die Dokumentation im Living Style Guide relevant ist.

### Kommentare für Inline Code Dokumentation

Grundsätzlicher Aufbau/Syntax eines Kommentars

```
/**
 * Kurz-Beschreibung im Doxygen Kommentar Format
 * 
 * Ausführliche Beschreibung, die detailiert die Aufgabe des Codes erklärt.
 * Links und Beispiel Markup sind oft hilfreich oder gar notwendig.
 * versehen (Bsp. `.example`).
 *
 * Example HTML:
 *
 * <ul class="example">
 *      <li></li>
 *      ...
 * </ul>
 */
```

Ist es sinnvoll einzelne Deklarationen zu erklären, werden sie wie folgt notiert.

```
/**
 * Kurz-Beschreibung
 * 
 * Ausführliche Beschreibung. Klassennamen/Variablen) innerhalb der
 * Kommentare werden mit Backticks geschrieben.
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





### Kommentare für die Dokumentation im Living Style Guide

*in Arbeit*