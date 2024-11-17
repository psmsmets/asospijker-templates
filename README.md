# asospijker-templates

ASO Spijker LaTeX templates for documentclasses `article` and `beamer`.

Documentation and syntax are in Dutch only.


## Documentatie

Ga naar de documentatie van de template voor

* de [huisstijl](docs/algemeen.md);
* documentclass [article](docs/article.md);
* documentclass [beamer](docs/beamer.md);
* handige [packages](docs/packages.md) aanvullend aan de template.


## Installatie

### Windows

1. **Installeer MiKTeX**:
   - Download en installeer [MiKTeX](https://miktex.org/howto/install-miktex) via de officiële website. Kies bij de installatie voor de optie om alle pakketten automatisch te installeren als dat gevraagd wordt.
   
2. **Download de template**:
   - [Download de template](https://github.com/psmsmets/asospijker-templates/archive/refs/heads/main.zip) en plaats de map op een vaste locatie op je computer.

3. **Verplaats of kopieer bestanden naar de lokale TeX-map**:
   - Open Windows Verkenner en navigeer naar de map waar je de template hebt opgeslagen.
   - Kopieer de bestanden in de template-map naar de MiKTeX root directory. De standaardlocatie is:
     ```
     C:\Users\<jouw gebruikersnaam>\AppData\Roaming\MiKTeX\2.9\tex\latex\misc
     ```
     Als de map `misc` niet bestaat, maak deze dan aan.

4. **TeX-database bijwerken**:
   - Open de MiKTeX Console (zoek in het startmenu naar "MiKTeX Console").
   - Klik op "Tasks" (of "Taken") en selecteer "Refresh file name database".
   - Sluit de console.

**Optie zonder command-line interactie**: Gebruik de MiKTeX Console:
   - Start de MiKTeX Console.
   - Ga naar "Settings" > "Directories".
   - Voeg de map toe waarin je de template hebt opgeslagen, zodat MiKTeX deze bestanden kan vinden.

### MacOS

1. **Installeer TeX Live**:
   - Download en installeer [TeX Live](https://tug.org/texlive/) voor MacOS.

2. **Download de template**:
   - [Download de template](https://github.com/psmsmets/asospijker-templates/archive/refs/heads/main.zip) en verplaats deze naar een plek waar de map kan blijven staan.

3. **Verplaats of link de templates**:
   - Kopieer of maak een symlink naar `/Library/texmf/tex/latex/misc`:
     ```bash
     ln -s /path/to/asospijker* /Library/texmf/tex/latex/misc/
     ```
   - Als je geen terminal wilt gebruiken, kun je deze map handmatig verplaatsen via Finder:
     - Navigeer naar `/Library/texmf/tex/latex/`.
     - Maak een map `misc` aan als die niet bestaat.
     - Kopieer de bestanden naar deze map.

4. **TeX-database bijwerken**:
   - Open de terminal en voer het volgende commando uit om de database bij te werken:
     ```bash
     texhash
     ```
   - Bij gebruik van een GUI-tool zoals TeXShop zal de database vaak automatisch worden bijgewerkt.

---

Als je vragen hebt of tegen problemen aanloopt, raadpleeg dan de documentatie van MiKTeX of TeX Live, of neem gerust contact met mij op.
