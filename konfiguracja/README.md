# KONFIGURACJA

## Username i e-mail
Uwaga: jeśli jest spacja to potrzebny cudzysłów!
> git config --global user.name "Imię Nazwisko"

E-mail będzie częścią historii projektu.
> git config --global user.email my@email.com


## Komendy
ustawia konfigurację
> git config klucz wartość

czyści konfigurację
> git config --unset klucz

wyświetla konfigurację
> git config klucz

wyświetla całą konfigurację
> git config --list

wyświetla skonfigurowany email
> git config user.email


## Śledzenie zmian
Ustawiam domyślny edytor na NANO
> git config core.editor nano

instaluję meld - graficzne narzędzie do diff
> sudo apt install meld

ustawiam meld jako domyślne narzędzie
> git config --global diff.tool meld

> git config --global difftool.prompt false

> git config --global merge.tool meld
