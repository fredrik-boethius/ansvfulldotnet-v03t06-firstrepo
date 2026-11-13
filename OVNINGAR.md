# Gitövningar

Följ övningarna i ordning. Skriv kommandona i terminalen från repots mapp. Byt ut exempel som `<filnamn>` mot det faktiska namnet på din fil.

## 1. Klona din kopia

Skapa först ett eget repo från lärarens template på GitHub. Klona sedan URL:en till ditt repo och gå in i mappen. Om du redan har gjort detta enligt README kan du gå vidare.

```text
git clone <URL-till-ditt-repo>
cd <mappnamnet>
```

Kontrollfråga: Var finns nu din repoarbetskopia? Vilket repo på GitHub är kopplat till den?

## 2. Ändra en fil och granska ändringen

Öppna `elevprofil.md`. Fyll i ditt namn och skriv en mening om vad du vill lära dig. Spara filen och kör:

```text
git status
git diff
```

Kontrollfråga: Vilka rader har ändrats? Har Git sparat ändringen i en commit ännu?

## 3. Lägg till ändringen

Välj filen till nästa commit och granska den igen:

```text
git add elevprofil.md
git diff --staged
git status
```

Kontrollfråga: Vad visar `git diff --staged`? Vad har ändrats efter att du körde `git add`?

## 4. Skapa en commit

Spara den valda ändringen i din lokala Git-historik:

```text
git commit -m "Lägg till min elevprofil"
git status
```

Kontrollfråga: Vad betyder det att arbetsmappen är ren? Var finns commiten just nu?

## 5. Skicka commit till GitHub

Skicka committen till ditt repo på GitHub:

```text
git push
```

Öppna ditt repo på GitHub och kontrollera att `elevprofil.md` och commitmeddelandet finns där. Om Git visar ett förslag med `-u` första gången, kör kommandot som Git föreslår.

Kontrollfråga: Vad finns nu både på datorn och GitHub?

## 6. Skapa och byt branch

Skapa en branch för ett eget förslag. Kontrollera branchlistan och byt till din nya branch:

```text
git branch
git branch mitt-forslag
git checkout mitt-forslag
git branch
```

Stjärnan visar vilken branch du står på. Kontrollera att den står vid `mitt-forslag`.

Kontrollfråga: Vad heter branchen som är aktiv?

## 7. Ändra och spara på branchen

Öppna startfilen `mitt-forslag.md`. Lägg till ett eget förslag på något du vill ha i klassens repo och spara filen. Granska, lägg till och spara ändringen:

```text
git diff
git add mitt-forslag.md
git diff --staged
git commit -m "Lägg till mitt förslag"
```

Kontrollfråga: Vilken branch innehåller den nya committen?

## 8. Jämför brancher

Jämför huvudbranchen `main` med din förslagsbranch:

```text
git diff main..mitt-forslag
```

Läs igenom skillnaderna. Byt tillbaka till huvudbranchen och kontrollera filerna:

```text
git checkout main
git status
```

Kontrollfråga: Vilken fil finns bara i `mitt-forslag`? Varför syns den inte när du står på `main`?

## 9. Hämta information med fetch

På GitHub-webben öppnar du filen `klassens-info.md` i ditt repo. Redigera den direkt på GitHub: lägg till en kort rad under rubriken och committa ändringen på branchen `main`.

Gå tillbaka till terminalen. Hämta information om ändringen och jämför din lokala `main` med GitHub-versionen:

```text
git fetch
git status
git diff main..origin/main
```

Kontrollfråga: Vilken rad har ändrats på GitHub? Har `git fetch` ändrat filen på din dator?

## 10. Integrera ändringen med pull

Se till att du står på `main` och att du inte har osparade ändringar. Hämta och integrera sedan ändringen från GitHub:

```text
git checkout main
git pull
git status
```

Öppna `klassens-info.md` på datorn och kontrollera att din nya rad finns där.

Kontrollfråga: Vad gjorde `git pull` med ändringen som du tidigare såg med `git fetch`?

## 11. Märk en version med tag

Sätt en versionsetikett på den aktuella committen och visa dina taggar:

```text
git tag -a v1.0 -m "Första genomförda Gitövningen"
git tag
```

Skicka taggen till GitHub:

```text
git push origin v1.0
```

Kontrollera taggen under ditt repo på GitHub.

Kontrollfråga: Vad pekar taggen på? Vad skiljer en tagg från en branch?

## 12. Repetition

Gå till `mitt-forslag` igen och kontrollera att din fil finns kvar:

```text
git checkout mitt-forslag
git status
```

Skriv kort med egna ord i `mitt-forslag.md` hur du använde `diff`, `add`, `commit` och `push`. Granska ändringen och spara den som en ny commit. Skicka branchen till GitHub:

```text
git diff
git add mitt-forslag.md
git diff --staged
git commit -m "Reflektera över Gitövningen"
git push -u origin mitt-forslag
```

Om Git säger att branchen redan har en upstream kan du använda `git push`.

Avsluta med att förklara för en klasskamrat skillnaden mellan `fetch` och `pull`.

