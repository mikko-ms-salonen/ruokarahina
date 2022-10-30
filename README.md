Ruokarähinä fullstack by Mikko Salonen

Sovelluksessa tulee olla seuraavat toiminnot:
    Eri ravintosisältöjen haku ulkoisesta lähteestä (esim. Fineli API tai jokin muu vastaava kuten CSV-tiedosto) - OK
    Ravintosisältöjen muuntaminen hahmoluokkiin - OK
    Logiikan toteutus kahden ruokahahmon väliseen kaksintaisteluun - OK
    Tulosten esitys tekstimuotoisena rajapinta vastauksena tai visuaalisesti Frontendilla - Molemmat OK

Riippuvuudet:
*~*~*
Python-moduulit Django & requests

Käyttö (Windows):
*~*~*
Paketoin mukaan Python virtual environmentin, jossa on Django ja requests jo asennettuna. Käyttäjän tulee aktivoida venv ajamalla 

	django_venv\Scripts\activate.bat 

Komentorivillä.

Tämän jälkeen käynnistetään Django webserver ajamalla

	py manage.py runserver

kansiossa

	django_venv\mysite\

Applikaatio löytyy osoitteesta

	http://localhost:8000/rahina/

Applikaatio pyytää täyttämään kaksi kenttä, hahmo 1 ja hahmo 2. Näihin tulee hakusana Finelin API -hakua varten. Esimerkiksi voidaan täyttää

	Hahmo 1 Porkkana Hahmo 2 Paprika

Painetaan OK. Applikaatio siirtyy http://localhost:8000/rahina/taistelu/?... -näkymään, joka esittää haun tulokset ja taistelun tehtävänannossa annetun tyylin mukaan.

Vaihtoehtoinen näkymä löytyy osoitteesta

	http://localhost:8000/rahina/taistelu2/

Tässä näkymässä taistelun kulku esitetään yksi vuoro kerrallaan, kun käyttäjä painaa "Go" -painiketta.

Miten Se Toimii?
*~*~*
Tehtävänannon mukainen ohjelmalogiikka on kehitetty ruokarahina.py -moduulissa. Fineli API -haku tapahtuu hahmoluokan konstruktorissa. Haku toimii yrittää löytää täsmällisen tuloksen. Jos täsmätulosta ei löydy, haku palauttaa ensimmäisen tuloksen jossa esiintyy annettu hakusana. Taisteluluokka implementoi taistelulogiikan ja toimii taistelun kulun tallennuspaikkana. Moduulia voi ajaa omana ohjelmanaan komentoriviltä.

Fullstack-toteutus on tehty Django-stackilla. Käytän Djangoa koska se on helppo ja nopea, erityisesti Python-backendeille. Taso on "proof-of-concept" luokka, käytettävyyttä tai ulkoasua en ehtinyt hiomaan.

Haluan osallistua arvontaan etc. Minuun voi ottaa yhteyttä

	Email: mikko.ms.salonen@iki.fi
	Puh.: 044 516 0243