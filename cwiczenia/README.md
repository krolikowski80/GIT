# Ćwiczenia z gitem

## Git Merges

W tym laboratorium wykorzystasz swoją wiedzę na temat historii pliku w drzewie Git, aby sprawdzić istniejące 
repozytorium i wprowadzić w nim zmiany. Przetestujesz również to, czego się nauczyłeś o wycofywaniu zatwierdzeń po złych commitach, 
aby naprawić skrypt w repozytorium i uruchomić go w celu uzyskania poprawnych wyników.

Co będziesz robić

* Sprawdź status i historię istniejącego repozytorium Git 
* Utwórz gałąź
* Zmodyfikuj treść w gałęzi
* wycofaj zmiany
* Scal gałąź

Utwórz gałąź
> git branch improve-output 

wejdź na gałąź
> git checkout improve-output

dokonuję zmian w odpowiednuim  pliku
 
> git add ten_plik

> git commit -m ‘commit message’

> git log --oneline

przywracam commit z działającym plikiem. Ta metoda tworzy nowy commit na aktualnym branchu
> git revert <commit ID> 

Teraz należy zrobić merge z do mastera

> git checkout master

> git merge improve-output
