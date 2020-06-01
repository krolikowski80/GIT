# PRACA ZDALNA

## Klonowanie repo
> git clone /path/to/repo.git /gdzie/  . oznacza TUTAJ a brak podania miejsca tworzy katalog jak nazwa zdalnego

Jeżeli repo zostało sklonowane to jest faktycznie ustawione tak, jak powinno być
Rozkodujmy "refs/..."
refs/remotes/origin/master:
• refs - referencje do commitów (wszystkie)
• remotes - commity w zdalnych repozytoriach
• origin - zdalne repo o nazwie "origin"
• master - gałąź "master" w repo "origin"

wszystkie zdalne repo
> git remote

Więcej info o origin
> git remote show origin

Więcwj info o powiązaniu branch z reo zdalnym
> git branch -vv

Comit bez zmian w kodzie
> git commit --allow-empty -m "ping remote"

## Tworzenie repo zdalnego czyli Bare. Jest ono puste i służ tylko do wymiany plików.
> mkdir server_repo.git
> cd server_repo.git
> git init --bare

## Jeżeli chcę własny katalog z kodem ustawić jako repo i wypchnąć je na zewnątrz:

Połączenie między repozytoriami
W katalogu z lokalnym repo, dodaje połączenie do naszego nowego bare repo - lub innego - w gitHub
>git remote add origin ../server_repo.git

## Wysłanie commitów
Wypchnij do zdalnego repo o nazwie orygin moją gałąź o nazwie master i zmapuj te nazwy ze sobą razem
Od teraz: "git push" bez tłumaczenia dokąd zmiany mają być wysłane.
> git push origin master -u


Dość tych masterów! Inne nazwy gałęzi
Dwukropek Oddziela lokalną nazwę od nazwy "zdalnej":
> git checkout -b my_experiment_branch
> git push origin -u my_experiment_branch:nowa_nazwa

Skasowanie zdalnej gałęzi
> git push origin :zdalna_nazwa_gałęzi

lub
> git push origin --delete zdalna_nazwa_gałęzi

kasowanie lokalnego odnośnika do zdalnej gałęzi
> git remote remove nazwa_gałęzi

Pokaż wszystkie gałęzie
> git branch -a


Czy nasz "push" wykonał pełny "backup"?
> gitk -all

Nie ma tagów!
Nie byłoby też gałęzi innych niż "master"!

Robię pełen backup
> git push zdalne_repo --mirror

Remote rename
> git remote rename obecna_nazwa nowa_nazwa

## Pobieranie zmian
tracking branch czyli Lokalna gałąź reprezentująca zdalną gałąź, np. "origin/master".
Nie pracujemy na niej bezpośrednio. 
Jest aktualizowana przy operacjach integrujących zmiany ze zdalnego repozytorium (fetch / pull / push).

Aktualizuję lokalną reprezentację zdalnej gałęzi (remote/orygin/masret) - pozostaeiając lokalną gałąź bez zmian
> git fetch - pobranie zmian
> gitk --all

origin/master ma najnowszy commit, a lokalny master - jeszcze nie
> git status

konsola potwierdza - "can be fast-forwarded" -> fast-forward to "bezpieczny" merge! 
Fetch jest bezpieczne. Nie dotyka lokalnych ("naszych") gałęzi.

pull = fetch + merge - Zmiany są ściągane (fetch) a potem łączone (merge) do lokalnej gałęzi
> git pull
