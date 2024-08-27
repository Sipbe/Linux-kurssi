# h1 - Oma Linux

## Asennus

Aloitin tehtävän latamaalla koneelleni (Lenovo) Virtualboxin. Asennus sujui nopeasti ja sovelluksen avattuani pääsin luomaan virtuaalikoneen. Virtuaalikoneen luominen alkoi kohdasta "New", jonka jälkeen avautui "Create Virtual Machine" -ikkuna. Siirryin ikkunan alareunasta Expert Modeen, ja aloin täyttämään tarvittavia tietoja. Näihin tietoihin lukeutui mm. nimitiedot ja käyttöjärjestelmä sekä laitteistoon ja kovalevyyn liittyvät asetukset. 

Kun olin täyttänyt tarvittavat tiedot, loin virtuaalikoneen klikkaamalla painiketta "Finish".

Seuraavaksi siirryin "Settings" -kohtaan Virtualbox Managerin kautta  ja valitsin kohdan "Storage". Valitsin "Empty" CD-levyn ja edelleen kohasta "Attributes" painoin uudestaan CD-levyä. Tähän kohtaan valitsin "debian-live..." -tiedoston ja klikkasin sen jälkeen kohdasta "OK" hyväksyäkseni muutokset.

## Käynnistys

Asennuksen jälkeen siirryin virtuaalikoneeni käynnistysvaiheeseen. Virtuaalikoneen käynnistäminen tapahtui painamalla kohtaa "Start". Ruudulle avautuvasta "Boot Menu" -kohdasta valitsin "Live system (amd64)" vaihtoehdon. Valinnan jälkeen pääsin ensimmäistä kertaa Linuxini työpöydälle. 

Ensimmäisenä Linuxissa testasin sen toimivuutta selaimessa. Hakusanaksi selaimeen valitsin "Koira" ja se tuottikin onnistuneen lopputuloksen.

Seuraavaksi siirryin asentamaan Debianin klikkaamalla "Install Debian" -kuvaketta. "Welcome" -kohdasta valitsin kieleksi englanti, "Location" -kohdasta valitsin Suomen, "Keyboard" -kohdasta "Generic 105-key PC"; "Finnish" ja "Default", "Partitions" -kohasta "Erase Disk" sekä "Users" -kohassa täytin nimitiedot itsestäni ja koneesta sek' valitsin käyttäjälleni salasanan. Tämän jälkeen ruudulle ilmestyi sisäänkirjautuminen, jossa aikaisemmin täyttämilläni tiedoilla pääsin kirjautumaan sisälle ja takaisin työpöydälleni.

# Lähteet
Karvinen, Tero. 21.8.2024. Oppitunti. Linux Palvelimet.

Karvinen, Tero. 2023. Install Debian on Virtualbox. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/

Karvinen, Tero. 4.6.2006. Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/
