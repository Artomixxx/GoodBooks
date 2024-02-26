# GoodBooks
Projekt w czystym PHP
Projekt GoodBooks

Autorzy: Wiktoria Zawadzka, Cezary Żak

Podział pracy:
Wiktoria - front-end aplikacji, index.php, panel logowania
Cezary - obsługa logowania, panel dla administratora/moderatora i operacje na bazie danych

Opis
GoodBooks to aplikacja internetowa, która umożliwia użytkownikom wyszukiwanie i przeglądanie książek w określonym zakresie lat lub z określonego roku, korzystając z informacji dotyczących autora lub tytułu. Pozwala na wyświetlenie szczegółów wybranej przez użytkownika książki, takich jak okładka książki oraz jej krótki opis. Dane te są pobierane z API Google Books. Ponadto, aplikacja oferuje możliwość eksportowania wyników wyszukiwania do różnych formatów, takich jak XML, JSON lub SQL. Administrator strony i moderatorzy mają dostęp do bardziej zaawansowanych funkcji - operacji CRUD, w zależności od ich roli.

Lista przykładowyc pytań: 
1. Które 10 książek z zakresu lat 2000-2010 mają najlepsze oceny?
2. Które 10 książek z zakresu lat 2000-2010 i o części tytułu "Harry" mają najlepsze oceny?
3. Jakie są najlepsze książki autora "Tolkien"?
4. W którym roku została wydana książka "words of radiance" i jaką ma ocenę?
5. Jaką okładkę ma książka "Nightingale" oraz jaki ma opis?
6. Jacy są autorzy najlepszych 10 książek z roku 1969 i jakie mają oceny?

Całość jest napisana w języku programowania PHP, HTML, JavaScipt i CSS

Wykorzystywane dane:
Baza danych: https://www.kaggle.com/datasets/zygmunt/goodbooks-10k
API Google Books


Baza danych MySQL phpMyAdmin: plik baza_exported.sql
W jego skład wchodzą 2 bazy danych: goodbooks (z danymi o książkach) oraz logowanie (zawierającą informacje o użytkownikach)

REST
W pliku moderator_panel.php jest wysłanie żądania POST do dodaj_ksiazke.php

ORM
W panelu administratora wykorzystywany jest ORM Eloquent dostarczany przez framework Laravel. Jest on napisany ręcznie ze względu na brak frameworków w projekcie. Tworzy połączenie, definiuje model dla tabeli "books" i używa go do operacji na bazie danych.

Tokeny JWT
Po zalogowaniu jako administrator lub moderator, tworzony jest token JWT, który jest przechowywany w sesji. Po tokenie sprawdzane jest, czy użytkownik zalogował jako administrator lub moderator na stronach, które wymagają uprawnień administratora/moderatora.

Poziomy Izolacji
Został użyty poziom izolacji "READ COMMITTED".

Aby uruchomić aplikację należy posiadać XAMPP, uruchomić moduł Apache oraz MySQL, wejść na 'Admin' przy MySQL, zaimportować bazę 'baza_exported.sql' następnie uruchomić URL: http://localhost/Projekt_GoodBooks/index.php.

