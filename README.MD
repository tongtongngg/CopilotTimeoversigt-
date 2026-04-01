# DTU Automatisk Timeoversigt

Dette værktøj er designet til at gøre arbejdet med tidsregistrering langt lettere. Det tager de rå-data fra Fusion og sørger automatisk for at regne timerne ud og fordeler dem rigtigt for hver medarbejder. Derudover giver den også et hurtigt og klart opsummering over, hvordan tiden bliver brugt, uden at skulle lave manuelle beregninger.


## Formål

Værktøjet automatiserer de centrale beregninger i forbindelse med timeoversigter:

- Den finder automatisk frem til, hvor mange timer den enkelte medarbejder skal lægge (normtid).
- Planlægningsgrader: Den viser hurtigt, hvor meget af medarbejderens tid der er planlagt ud.  
- Automatisk fordeling af timer på de rigtige projektkoder (UK-koder)
- Automatisk opsummering pr. sektion  
- Identifikation af datamæssige problemer (DATA ISSUES)  
- Visuel formatering (trafiklys, talformatering m.m.)

---

<br>

## Brugervejledning

For at Copilot Agenten kan behandle din timeoversigt har den brug for to filer som du skal uploade i Copilot chatten. 

### **1. RUNME.py (Python-behandlingsfil)**  
Agenten bruger denne fil til at udføre alt beregning og formattering.

Download RUNME.py her:

> **[Download seneste version](https://github.com/tongtongngg/AOER-Work-Projects/releases/download/v1.0/RUNME.py)**


### **2. Rådata fra Fusion (CSV-format)**  
Rådataen trækkes fra Fusion som en CSV fil. En download guide for det kan findes ved at trykke på linket neden under.
Udover det indeholder linket også hele brugervejledningen med billeder.
Download vejledningen her:

> **[Download seneste vejledning](https://github.com/tongtongngg/AOER-Work-Projects/releases/download/v1.0/VejledningCopilot.pdf)**


*OBS:* Filen skal eksporteres som **CSV**, ikke Excel.


---

## Sådan bruger du værktøjet i Copilot-agenten

1.  **Åbn Copilot-agenten:** Vælg agenten **DTU Automatisk Timeoversigt**.
2.  **Upload filer:** Vedhæft både din **CSV-fil** og **RUNME.py** i den samme besked.
3.  **Aktiver processen:** Skriv følgende kommando i chatten:

    > ### **`Kør timeoversigten.`**
    > *OBS: Vent på, at begge filer er færdiguploadet i Copilot-chatten, før du sender beskeden.*

    > [!NOTE] 
    > **Fejlhåndtering:**
    > Hvis du får en fejlbesked om, at "RUNME.py ikke er indlæst korrekt" eller kun er delvist indlæst, så skriv: **"Indlæs RUNME og CSV fuldt og kør igen"**. Hvis den stadig fejler, så åbn en ny chat og prøv igen.

4.  **Vent på behandlingen:** Når du har sendt beskeden, håndterer agenten automatisk resten:
    * **Databehandling:** Agenten læser filerne og afvikler Python-koden.
    * **Kvalitetstjek:** Systemet sikrer, at dataene er korrekt behandlet.
    * **Resultat:** Du modtager et direkte download-link til din færdige Excel-fil.
---

> [!NOTE]
> **OBS:** Det kan tage et par minutter for Copilot agenten at generere den fulde timeoversigt. Giv den tid til at færdiggøre beregningerne. Forlad ikke siden mens den kører.


## Link til Copilot Agenten for automatisk behandling
> **[Copilot Agent link](https://m365.cloud.microsoft/chat/?titleId=T_0fe64bcc-3205-af7a-37d0-1f3927a96023&source=embedded-builder)**

*OBS:* Virker kun for medarbejdere og studerende med en DTU-mail

<br>


## Funktioner

Værktøjet behandler udtræk fra Fusion og genererer automatisk følgende:

* **Beregnet normtid:** Beregner normtid pr. medarbejder baseret på ansættelsesgrad i Fusion og antallet af måneder, medarbejderen er ansat i det nuværende år. Der afrundes til halve måneder.
* **Planlægningsgrad:** Beregner de planlagte timer i forhold til medarbejderens normtid.
* **Fordeling på underkonti:** Fordeler de planlagte timer på underkonti i både faktiske tal og procentvis fordeling.
* **Sektionsoverblik:** Genererer et ark, hvor data er summeret op pr. sektion.
* **Fejlhåndtering (Data Issues):** Opretter et separat ark til eventuelle datafejl, f.eks. hvis en ansættelsesgrad mangler i systemet.

---

## Arbejdsgang

1.  **Udtræk:** Lav et hurtigt dataudtræk fra Fusion.
2.  **Behandling:** Kør værktøjet med det rå dataudtræk som input.
3.  **Gennemgang:** Analyser de genererede ark for sektionsoverblik og individuelle opgørelser.

---

## Teknisk Logik

| Funktion | Beskrivelse |
| :--- | :--- |
| **Afrunding** | Ansættelseslængde afrundes til nærmeste 0,5 måned. |
| **Normtid** | Beregnes som: $\text{Ansættelsesgrad} \times \text{Måneder ansat}$ |
| **Datafejl** | Rækker med manglende stamdata flyttes automatisk til arket "Data Issues". |

