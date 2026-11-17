# Cupid in a Blender (arbeidstittel)

Et Unity-spill utviklet av Isak, alene. Dette er et lidenskapsprosjekt der han eksperimenterer med nye ting. Prosjektet er helt i startfasen.

## Hvordan du skal jobbe med Isak

- Svar på norsk, i en uformell tone.
- Isak kommer fra Unity Visual Scripting og er ikke vant til å skrive C# selv. Forklar hva koden gjør i vanlige ord, og hvorfor du valgte løsningen.
- Jobb i små steg. Én ting om gangen, så endringene er lette å forstå og lette å angre.
- Etter hver endring: si nøyaktig hva Isak må gjøre i Unity-editoren for å teste den (hvilket objekt skriptet skal ligge på, hvilke felt som må fylles ut i Inspector, hva han skal trykke på).
- Introduser nye konsepter (for eksempel ScriptableObjects) kort første gang de trengs, og gå i dybden først når han ber om det.
- Spør før du gjør større strukturelle valg. Foreslå gjerne, men ikke bygg et stort system uten at han har sagt ja.
- Si fra tydelig hvis noe han ber om er en dårlig idé eller vil få scopet til å vokse.

## Git

- IKKE commit eller push uten at Isak ber om det. Han ser over endringene i Fork og committer selv.
- Store binærfiler (bilder, lyd, PSB) går via Git LFS, se `.gitattributes`.
- Ikke endre `.gitignore` eller `.gitattributes` uten å spørre.

## Unity-regler

- Motor: Unity 6, Universal 2D (URP med 2D-renderer). Sjekk eksakt versjon i `ProjectSettings/ProjectVersion.txt`.
- Aldri rør `Library/`, `Temp/`, `Logs/`, `Obj/` eller `UserSettings/`. De er generert av Unity.
- Aldri lag, rediger eller slett `.meta`-filer for hånd. Unity lager dem selv. Hvis en fil skal flyttes eller gis nytt navn, be Isak gjøre det inne i Unity-editoren, så følger `.meta`-filen med og referanser ikke brytes.
- Ikke rediger scener (`.unity`), prefabs (`.prefab`) eller andre Unity-YAML-filer direkte. Skriv skriptet, og forklar Isak hvordan han kobler det opp i editoren.
- Ikke rediger Visual Scripting-grafer. De egner seg ikke for tekstredigering.
- Ikke endre `Packages/manifest.json` eller filer i `ProjectSettings/` uten å spørre først.
- Du kan ikke se eller kjøre Unity-editoren. Isak tester og melder tilbake med feilmeldinger fra konsollen.

## Kode

- C#-skript ligger under `Assets/Scripts/`, sortert i undermapper etter funksjon.
- Ett skript, én oppgave. Korte, lesbare skript framfor smarte.
- Bruk `[SerializeField] private` for felt som skal settes i Inspector, med `[Tooltip]` der det hjelper.
- Kommentarer på norsk, kode (klasse-, metode- og variabelnavn) på engelsk.
- Ingen tredjepartspakker eller nye Unity-pakker uten å spørre.

## Om spillet

Sjanger: en blanding av klassisk point and click-eventyr og deduksjonsspill. Inspirasjonene er Monkey Island, Wadjet Eye-spillene og The Case of the Golden Idol.

Kjernemekanikk:
- Spilleren utforsker områder og plukker opp clues: ord, objekter og handlinger.
- Clues plasseres i menyer og rebuser, i en slags rapportmeny.
- Hvert område eller rom kan ha egne rebuser.

En løst rebus kan låse opp nye områder og dialoger, oppsummere det spilleren har funnet ut, og drive historien fremover.

Historieobjekter og forgreninger:
- En rebus kan ha flere gyldige løsninger, to eller tre.
- Løsningen spilleren velger, blir et historieobjekt som fungerer som nøkkel videre.
- Når historieobjektet er valgt, låses det, og historien tar en av flere grener med små og store endringer utover.
- Spilleren kan få vite at det finnes flere løsninger. Det skal føles litt skummelt å låse en løsning.

Eksempel: Du er detektiv og våkner på kontoret om morgenen. For å gå ut døra trenger du et historieobjekt. Objekter, nøkkelord og handlinger på kontoret kan settes sammen til to eller tre ulike løsninger, som hver åpner døra til sin gren av historien.

Ramme: scopet må ikke bli for stort.

## Status

Tomt prosjekt. Ingenting er bygget ennå. Første mål er en liten test: klikk på et objekt i en scene og få et clue lagt i en liste.
