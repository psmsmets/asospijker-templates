# asospijker-templates

ASO Spijker LaTeX templates for article and beamers.

Documentation and syntax are in Dutch.

## Algemeen

### Huisstijl kleuren

| Syntax | RGB | grijswaarde |
| ----------- | ----------- | ----------- |
| `spijker-blauw` | {0,171,200} | {0.10} |
| `spijker-geel` | {255,213,77} | {0.80} |
| `spijker-rood` | {228,102,88} | {0.30} |
| `spijker-lichtrood` | {246,176,135} | {0.60} |

Extra varianten
 * 15% donkerder: `spijker-donkerblauw`, `spijker-donkergeel`, `spijker-donkerrood`
 * 15% lichter: `spijker-lichtblauw`, `spijker-lichtgeel`

## documentclass = article

### Types hoofding voor `\maketitle`

| Syntax | Omschrijving |
| ----------- | ----------- |
| `proefwerk` | Hoofding voor proefwerken. |
| `test` | Hoofding voor testen. |
| `taak` | Hoofding voor taken en remediëringsoefeningen. |
| `practicum` | Hoofding voor practica. |
| `logo` | _standaard hoofding_ met Spijker logo bovenaan. |
|        | _geen van bovenstaande opties geeft een standaard document hoofding_ |

Alle bovenstaande package-opties herdefiniëren de `\maketitle` functie.

### Algemene opties

| Syntax | Omschrijving |
| ------ | ------------ |
| `dubbelzijdig` | Asymmetrische marges voor dubbelzijdig printen en inbinden.  |
| `print` | Veranderen kleuren in grijswaarden (niet bij afbeeldingen). Standaard is `screen`.  |
| `show` | Maak de `antwoorden` onderaan het document leesbaar. Standaard is `hide`. |

### Voorgedefiniëerde vakken

| Syntax | Omschrijving |
| -------| ------------ |
| `fysica` | Aangepaste control squences per hoofding voor het vak fysica. Baseline wordt `barst van wetenschappen`. |
| `wiskunde` | Aangepaste control squences per hoofding voor het vak wiskunde. Baseline wordt `barst van wiskunde`. |

Voorgedefiniëerde control sequences kunnen nog steeds aangepast worden.

### Control sequences voor `\maketitle`

Alle mogelijke control sequences voor de verschillende hoofdingen. Niet alle commando's zijn relevant voor elke hoofding.

| Syntax | proefwerk | test | practicum | logo en _standaard_ |
| ------ | :-------: | :--: | :-------: | :-----------------: |
| `\leerkracht{}` | v | v | v | o |
| `\vak{}` | v | v | v | o |
| `\module{}` | - | o | o | o |
| `\klas{}` | v | o | - | - |
| `\naam{}` | o | o | - | - |
| `\voornaam{}` | o | o | - | - |
| `\titel{}` | o | o | o | v |
| `\cijfer{}` | v | o | o | - |
| `\datum{}` | v | o | o | o |
| `\hulpmiddelen{}` | v | - | - | - |
| `\toelichting{}` | v | o | o | - |

v = verplicht, o = optioneel, - = niet getoond

### Enviroments

#### antwoord en antwoord*
Genereer een antwoordveld in `Spijker-blauw` startend met `Antwoord: `:
```
\begin{antwoord}
   ...
\end{antwoord}
```

of een antwoordveld in `Spijker-blauw` zonder annotatie,
```
\begin{antwoord*}
   ...
\end{antwoord*}
```

#### antwoorden
Geneer een antwoordenbox, bijvoorbeeld voor onderaan je document, met de oplossingen van de oefeningen. Werk met `\label{vraag...}` in je `enumerate` van de opgaven.

De antwoordbox is leesbaar met de optie `show` en omgedraaid met de optie `hide`.

```
\begin{antwoorden}
    \begin{itemize*}
        \item[] \textbf{[\ref{vraag1}]} antwoord 1
        \item[] \textbf{[\ref{vraag2}]} antwoord 2
        \item[] \textbf{[\ref{vraag3}]} antwoord 3
    \end{itemize*}
\end{antwoorden}
```
 
### Voorbeeld
```
\documentclass[11pt, a4paper]{article}

\usepackage[fysica, test]{asospijker}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\module{Test}
\titel{Thema 1}
\leerkracht{P. Smets}
\cijfer{20}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\begin{document}

\maketitle

\end{document}
```

## documentclass = beamer

Deze template is nog in ontwikkeling.

### Algemene opties

| Syntax | Omschrijving |
| ------ | ------------ |
| `print` | Veranderen kleuren in grijswaarden (niet bij afbeeldingen). Standaard is `screen`.  |

### Voorbeeld

```
\documentclass[aspectratio=1610,slides,compressed]{beamer}

\usepackage[print]{asospijker}

\title{}
\subtitle[]{}
\author{}
\date{}

\begin{document}

\titleslide

\end{document}
```
