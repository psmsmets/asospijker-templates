# spijker-tex

ASO Spijker LaTeX templates

## Package-opties

### Types hoofding voor `\maketitle`

| Syntax | Omschrijving |
| ----------- | ----------- |
| `proefwerk` | Hoofding voor proefwerken. |
| `test` | Hoofding voor testen. |
| `practicum` | Hoofding voor practica. |
| `logo` | _standaard hoofding_ met Spijker logo bovenaan. |
|        | _geen van bovenstaande opties geeft een standaard document hoofding_ |

Alle bovenstaande package-opties herdefiniëren de `\maketitle` functie.

### Algemene opties

| Syntax | Omschrijving |
| ------ | ------------ |
| `dubbelzijdig` | Asymmetrische marges voor dubbelzijdig printen en inbinden.  |
| `print` | Veranderen kleuren in grijswaarden (niet bij afbeeldingen). Standaard is `screen`.  |
| `show` | Maak de `answerbox` onderaan het document leesbaar. Standaard is `hide`. |

### Voorgedefiniëerde vakken

| Syntax | Omschrijving |
| -------| ------------ |
| `fysica` | Aangepaste control squences per hoofding voor het vak wiskunde. Baseline wordt `barst van wiskunde`. |
| `wiskunde` | Aangepaste control squences per hoofding voor het vak fysica. Baseline wordt `barst van wetenschappen`. |

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

### Huisstijl kleuren

| Syntax | RGB | grijswaarde |
| ----------- | ----------- | ----------- |
| `spijker-blauw` | {0,171,200} | {0.00} |
| `spijker-geel` | {255,213,77} | {0.70} |
| `spijker-rood` | {228,102,88} | {0.30} |
| `spijker-lichtrood` | {246,176,135} | {0.50} |

Extra varianten
 * 15% donkerder: `spijker-donkerblauw`, `spijker-donkergeel`, `spijker-donkerrood`
 * 15% lichter: `spijker-lichtblauw`, `spijker-lichtgeel`
 
 ## Voorbeeld
```
\documentclass[11pt, a4paper]{article}

\usepackage[wiskunde, test]{spijkerarticle}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%\vak{Wiskunde}
\module{Test}
\titel{Thema 1}
\leerkracht{P. Smets}
%\datum{}
%\klas{}
\cijfer{20}
%\voornaam{}
%\naam{}
%\baseline{barst van wiskunde}
%\toelichting{eigen uitleg over de test}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\begin{document}

\maketitle

\end{document}
```
