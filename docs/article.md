# \documentclass{article}

```
\usepackage[]{asospijker}

\titel{asospijker-templates}

\begin{document}
    \maketitle
\end{document}
```

## Types hoofding voor `\maketitle`

| Syntax | Omschrijving |
| ----------- | ----------- |
| `proefwerk` | Hoofding voor proefwerken (standaard schriftelijk, optioneel mondeling). |
| `test` | Hoofding voor testen. |
| `taak` | Hoofding voor taken en remediëringsoefeningen. |
| `practicum` | Hoofding voor practica. |
| `logo` | _standaard hoofding_ met Spijker logo bovenaan. |
|        | _geen van bovenstaande opties geeft een standaard document hoofding_ |

Alle bovenstaande package-opties herdefiniëren de `\maketitle` functie.


## Algemene opties

| Syntax | Omschrijving |
| ------ | ------------ |
| `dubbelzijdig` | Asymmetrische marges voor dubbelzijdig printen en inbinden. |
| `indent` | Laat paragrafen inspringen. Standaard is `noindent`. |
| `print` | Veranderen kleuren in grijswaarden (niet bij afbeeldingen). Standaard is `screen`. |
| `show` | Maak de `antwoorden` onderaan het document leesbaar. Standaard is `hide`. |


## Voorgedefiniëerde vakken

| Syntax | Omschrijving |
| -------| ------------ |
| `fysica` | Aangepaste control squences per hoofding voor het vak fysica. Baseline wordt `barst van wetenschappen`. |
| `wiskunde` | Aangepaste control squences per hoofding voor het vak wiskunde. Baseline wordt `barst van wiskunde`. |

Voorgedefiniëerde control sequences kunnen nog steeds aangepast worden.

| Syntax | Omschrijving |
| ------ | ------------ |
| `nogrm` | Laat het gebruik van het `grafisch rekentoestel` *niet* toe. Standaard is `grm` (wel toegelaten). |
| `fb` | Laat het gebruik van het `formulebladen` toe. Standaard is `nofb` (niet toegelaten). |


## Control sequences voor `\maketitle`

Alle mogelijke control sequences voor de verschillende hoofdingen. Niet alle commando's zijn relevant voor elke hoofding.

| Syntax | proefwerk | test | practicum | logo en _standaard_ |
| ------ | :-------: | :--: | :-------: | :-----------------: |
| `\leerkracht{}` | v | v | v | o |
| `\vak{}` | v | v | v | o |
| `\module{}` | - | o | o | o |
| `\klas{}` | v | o | - | - |
| `\naam{}` | o | o | - | - |
| `\voornaam{}` | o | o | - | - |
| `\titel{}` | o | o | o | o |
| `\cijfer{}` | v | o | o | - |
| `\datum{}` | v | o | o | o |
| `\hulpmiddelen{}` | v | - | - | - |
| `\toelichting{}` | v | o | o | - |
| `\leerplandoelen{}` | - | o | - | - |
| `\lesdoelen{}` | - | o | - | - |
| `\feedbacklijst{}` | - | o | - | - |
| `\remedieringslijst{}` | - | o | - | - |

v = verplicht, o = optioneel, - = niet getoond

## Evaluatie

| Syntax | Omschrijving |
| ------ | ------------ |
| `evaluatie` | Voegt een volledige evaluatietabel (`zelfevaluatie` + `feedback` + `remediering`)toe aan de `test` en `taak` hoofdingen. |
| `zelfevaluatie` | Voegt de zelfevaluatietabel toe aan de `test` en `taak` hoofdingen. |
| `feedback` | Voegt de feedbacktabel toe aan de `test` en `taak` hoofdingen. |
| `remediering` | Voegt de remedieringstabel toe aan de `test` en `taak` hoofdingen. |

Je kan de voorgedefiëneerde lijsten met `feedback` en `remediëring` aanpassen via de variabelen `\feedbacklijst` en `\remedieringslijst`.

## Environments

### vragen
Genereer genummerde vragen met punten ofwel vooraan in het vet ofwel in de marge in een kader.
De omgeving `vragen` is een aangepaste `enumerate` lijst met aangepaste verticale marges.
```
\begin{vragen}

   \vraag[2] Eerste vraag ... % deze punten worden opgeteld bij het totale cijfer

   \vraag[1 pt] Andere vraag ...

   \vraag[3 ptn] Een grote vraag met deelvragen

    \begin{deelvragen}[series=reeks1]
        \deelvraag ...
        \deelvraag ...
    \end{deelvragen}

    ...

    \begin{deelvragen}[resume=reeks1]
        \deelvraag ...
    \end{deelvragen}
 
\end{vragen}
```

De functie `\vraag` is een uitbreiding op `\item` waar je optioneel het aantal punten van de vraag kan meegeven. 
Geef je enkel een getal als argument dan wordt ook het totale cijfer bepaald in de variable `\totaal`. 
Bij de weergave wordt automatisch de eenheid `pt(n)` toegevoegd. 

Om het cijfer van je test automatisch te laten uitrekenen zet je in de hoofding.
```
\cijfer{\totaal}
```
Je moet 2x compileren om het correcte cijfer te verkrijgen.

### antwoord en antwoord*
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

Om enkel een de tekst `Spijker-blauw` te maken kan je `\antw{...}` gebruiken.

### antwoorden
Geneer een antwoordenbox, bijvoorbeeld voor onderaan je document, met de oplossingen van de oefeningen. Werk met `\label{vraag...}` in je `enumerate` van de opgaven.

De antwoordbox is leesbaar met de optie `show` en omgedraaid met de optie `hide`.

```
\vfill
\begin{antwoorden}
    \begin{itemize*}
        \item[] \textbf{[\ref{vraag1}]} antwoord 1
        \item[] \textbf{[\ref{vraag2}]} antwoord 2
        \item[] \textbf{[\ref{vraag3}]} antwoord 3
    \end{itemize*}
\end{antwoorden}
```

### studiewijzer

```
\begin{studiewijzer}
	\studiewijzerKennen
	\studiewijzerKennenItem
		{de vier gevallen voor het gedrag op oneindig van een veeltermfunctie}
	\studiewijzerKunnen
	\studiewijzerKunnenItem
		{het gedrag op oneindig van veeltermfuncties noteren en interpreteren}
		{11, 12, 13, 14, 15, 17}
		{}
		{67, 68, 69, 70, 71, 72, 73, 74, 75, 76}
	\studiewijzerKunnenItem
		{het gedrag op oneindig van veeltermfuncties gebruiken om problemen op te lossen}
		{16}
		{}
		{77, 78}
\end{studiewijzer}
```

### labels in de kantlijn
Je kan bij vragen ook bijvoorbeeld het cijfer of een opmerking in de kantlijn plaatsen.

`\marginlabel{...}` = een tekstbox in de kantlijn uitgelijnd van waar je commando uitvoert.


`\marginlabelbox{...}` = een `\marginlabel` maar dan een met een Spijker-blauwe (of zwarte bij de optie `print`) tekstbox met witte letters.

### Cancel
Doorhalen van termen in vergelijkingen (`cancel` en `bcancel`) en eventueel met een toelichting (`cancelto` en `bcancelto`).
```
cancel{...}
bcancel{...}
cancelto[..]{...}{...}
bcancelto[..]{...}{...}
```

### Math commands
```
\abs{...}   % \left|#1\right|
\norm{...}  % \lVert#1\rVert
\der        % \mathrm{d}
\g          % 9{,}81\,\text{m/s}^2
```
 
## Voorbeeld
```
\documentclass[11pt, a4paper]{article}

\usepackage[fysica, test, puntenmarge]{asospijker}

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\module{Test}
\titel{Thema 1}
\leerkracht{P. Smets}
\cijfer{\totaal}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

\begin{document}

\maketitle

\begin{vragen}

    \vraag[3] Eerste vraag ...

    \vraag[7] Andere vraag ...

    \vraag[10] Een grote vraag met wat deelvragen.
    \begin{deelvragen}
        \deelvraag[2] ...
        \deelvraag[5] ...
        \deelvraag[3] ...
    \end{deelvragen}

\end{vragen}

\end{document}
```
