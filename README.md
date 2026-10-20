# Dag 8 · CSS-variabler och kodstruktur

*Modul 4, UI/UX & Frontendutveckling, Lexicon IT-Proffs*

## Vad du ska göra idag

Du städar sajtens CSS: du inför CSS-variabler för färger, typografi och avstånd, och delar upp den långa `styles.css` i flera filer.

## Bakgrund

Ett designsystem har *tokens*: namngivna värden för färg, text och avstånd. I kod heter de **CSS custom properties** (`--color-primary`). När ett värde finns på ett ställe kan du ändra det en gång och hela sidan följer med. En ordnad filstruktur gör att du (och andra) hittar rätt snabbt.

## Så arbetar du (samma som alltid)

1. **Forka** dagens repo på GitHub (*Fork → Create fork*).
2. **Klona din fork:** *Code → HTTPS → kopiera adressen*. I terminalen (Ctrl+ö i VS Code): `git clone <adressen>`. Öppna den nya mappen i VS Code och starta *Live Server*.
3. **Gör uppgiften.** Spara och kontrollera i webbläsaren efter varje steg. Gör en commit efter varje avslutat steg: `git add .` och `git commit -m "Beskriv vad du gjorde"`.
4. **Skicka upp** när du är klar: `git push`.
5. **Lämna in i Microsoft Forms.**

Fastnar du: skriv ner exakt var och vad du försökt, och ta det först i nästa handledda pass.

## Uppgiften steg för steg

### Steg 1. Skapa variablerna

Skapa mappen `css/` och filen `css/variables.css`. Deklarera variabler i `:root { ... }`: minst fem färger, två typsnitt och en avståndsskala (8, 16, 24, 32, 48 px). Namn: `--color-primary`, `--font-heading`, `--space-2`.

### Steg 2. Använd dem

Ersätt hårdkodade värden i resten av CSS:en med `var(--...)`. Börja med färgerna. Sidan ska se *exakt* likadan ut efteråt.

### Steg 3. Testa kraften

Ändra `--color-primary` i en fil och se hela sidan byta accentfärg. Ändra tillbaka.

### Steg 4. Dela upp filerna

Skapa `base.css` (reset, body, rubriker, länkar), `layout.css` (header, main, grid, footer, media queries) och `components.css` (knapp, kort, formulär). Flytta regler mellan filerna.

### Steg 5. Länka i rätt ordning

I `<head>` på båda sidorna: `variables.css` först, sedan `base`, `layout`, `components`. Ordningen spelar roll.

### Steg 6. Kontrollera att inget gick sönder

Jämför före och efter i webbläsaren på tre bredder. Ta bort den gamla `styles.css` när allt fungerar.

### Steg 7. Dokumentera

Överst i varje CSS-fil: en kommentar på en rad som beskriver vad filen innehåller.

## Kontrollista: så vet du att du är klar

- [ ] Det finns en `css/variables.css` med minst fem färger, två typsnitt och en avståndsskala.
- [ ] Färger och avstånd i resten av CSS:en använder `var(--...)`, inga hårdkodade hex-värden kvar utom i variabelfilen (och ev. vitt).
- [ ] CSS är uppdelad i minst `variables`, `base`, `layout` och `components`.
- [ ] Sidan ser exakt likadan ut som innan.
- [ ] Variablerna har samma namn och värden som dina tokens i Figma.
- [ ] Du har pushat till din fork och skickat in länken.

## Tips om du fastnar

- Variabeln fungerar inte? Kontrollera `var(--namn)` (två bindestreck) och att `variables.css` länkas FÖRE de andra.
- Glöm inte att `git add .` tar med hela `css/`-mappen. Kör `git status` före commit.
- Om det blir fel: kopiera tillbaka din gamla `styles.css` och försök igen, ett steg i taget.

## Inlämning

**Deadline: imorgon klockan 09.00.** Allt lämnas in i Microsoft Forms. Du behöver inte redovisa något muntligt.

I formuläret fyller du i:

1. Länk till din fork av det här repot.
2. Reflektion: Vilken fördel ser du med variabler som du inte hade tänkt på innan, och vilket variabelnamn är du mest nöjd med?

## Vill du mer? (frivilligt)

- Lägg till en `--shadow` och en `--radius`-variabel och använd dem.
- Skapa en mörk variant av paletten som byter variablerna i en `@media (prefers-color-scheme: dark)`.
