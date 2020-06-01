# PRACA LOKALNA

## Podstawy

inicjalizacja w katalogu bierzącym
> git init 

zapisuje plik w repo - (. = wszystkie nowe pliki)
> git add . 

Pozwala użytkownikowi interaktywnie przeglądać łatki, aby dodać je do bieżącego zatwierdzenia
> git add -p

Zatwierdza zmiany (. = wszystko) -m "opis zmiany"
> git commit . 

Automatycznie ustawia pliki
> git commit -a

Służy do wprowadzania zmian w zatwierdzeniach po fakcie, co może być przydatne do robienia notatek na temat danego zatwierdzenia.
> git commit --amend

Dokonuje nowego zatwierdzenia, które skutecznie wycofuje poprzednie zatwierdzenie. To trochę jak polecenie cofnięcia.
> git revert 

Sprawdzanie stanu repozytorium
> git status


# Przeglądanie logów (commitów)

pokazuje historię projektu
> git log 

* 4 ostatnie commity
> -n4							


* jednolinijkowe podsumowanie commita
> --oneline 					


* z przed 15 minut
> --since='{15 minutes ago}'	


* log w konsoli z narysowanymi gałęziami
> --graph --oneline 			

Pokazuje commity
> git show 		

pokazuje zawartość commita (i jego tagów)
> git show id_commita  		

pokaże commity pomiędzy od a do - tu idziemy od dołu do góry
> git show --online od..do 	

> ^ = karetka oznacza ilość commitów przed - np ^^^ to 3 komity przed. można to zastąpić ~3

> .. to zakres od..do - więc:


Może pokazywać różnice w różnych zatwierdzeniach
> git diff		

Alias ​​do --cached, pokaże wszystkie pliki przemieszczane po git add
> git diff --staged	



# Dodawanie i usuwanie plików

Podobnie do polecenia Linux `mv`, przenosi plik
> git mv		

Podobnie jak polecenie Linux `rm`, usuwa plik
> git rm		

zasadniczo resetuje repo, odrzucając niektóre zmiany.
> git reset 	



# Tagowanie commitów

nadaje tag commitowi = np. info o końcu inicjacji projektu - bez ID commita tag zostanie dodany do bieżącego commita
> git tag nazwa_taga (np. finish_init) 

nadaje taga do wskazanego commita
> git tag nazwa_taga ID_COMMITA 

tworzy anotated tag
> git tag nazwa_taga ID_COMMITA -a -m 'dodatkowa informacja w anotated tag'

wyświetla istniejące tagi
> git tag 

kasuje tag
> git tag -d nazwa_taga 



# Przechodzenie na commity, tagi, gałęzie

przejście na daną gałąź
> git checkout branch		

przejście na dany tag
> git checkout tag

przejście na dany commit
> git checkout SHA

przejście na... commit podany w dowolny sposób (np. git checkout master~4)
> git checkout ref

poprzedni commit (znal minus to poprzednia gałąź) 
> git checkout - 			

nowa gałąź + checkout
> git checkout -b another_new_branch  	

Służy do cofnięcia poprzedniego zatwierdzenia. Ta metoda tworzy nowy commit na aktualnym branchu
> git revert SHA

Służy do cofnięcia zmian w katalogu roboczym, które nie zostały jeszcze zatwierdzone. 
> git reset 						

Służy do kopiowania pliku z innego commita do bieżącego drzewa roboczego. 
Nie zatwierdza automatycznie zmian (commit).
> git checkout tag or SHA -- path/to/file.html 	



# Branch i merge

tworzy nową gałąź
> git branch my_new_branch 		

lista gałęzi (gwiazdka - aktualna gałąź (w Working Copy))
> git branch 				

kasuje gałąź 
> git branch -d or -D 			

zmienia nazwę aktualnego brancha
> git branch -m nowa_nazwa_gałęzi 	
