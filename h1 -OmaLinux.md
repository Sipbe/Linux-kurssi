# h1 - Oma Linux

#### *Kuvat ja koneen tiedot sekä tehtävä x) päivitetty raporttiin 29.8.24

## *x) Lue ja tiivistä
### Raportin kirjoittaminen
##### (https://terokarvinen.com/2006/raportin-kirjoittaminen-4/)
- Raportin tulee olla selkeä sekä helposti ymmärrettävissä ja toistettavissa
- On hyvä kertoa mikä onnistui, mikä ei onnistunut sekä miten ja missä ajassa testaaminen suoritettiin
- Raportissa tulee viitata lähteisiin 
- Raportin tulee olla todenmukainen ja aidosti omien tekojen ja ajatusten tuotos
### What is Free Software?
##### (https://www.gnu.org/philosophy/free-sw.html)
- Vapaalla ohjelmistolla tarkoitetaan sellaista ohjelmistoa, joka ei suinkaan välttämättä ole arvoltaan ilmainen, mutta sen sijaan vapaasti mm. muokattavissa, kopioitavissa ja myytävissä. Vapaaseen ohjelmistoon pääsee käsiksi siis kuka tahansa ja jokaisella on vapaat kädet ohjelmiston käsittelyn suhteen.
- Jotta ohjelmistoa voidaan kutsua "vapaaksi ohjelmistoksi", on sen täytettävä riittävällä tasolla seuraavat neljä (4) vapautta:
  ##### 1) Vapaus suorittaa ohjelmaa haluamallaan tavalla haluamaansa tarkoitukseen.
  ##### 2) Vapaus opiskella, miten ohjelma toimii, ja muuttaa sitä niin, että se vastaa haluamaasi (pääsy lähdekoodiin).
  ##### 3) Vapaus levittää kopioita auttaakseen muita.
  ##### 4) Vapaus jakaa kopioita ohjelmiston muokatusta versiosta, jotta muut voivat hyötyä muutoksista (pääsy lähdekoodiin).
- Mikäli ohjelmistoon liittyy oleennaisesti toinen toiminnallisuutta täydentävä ohjelmisto, on vapaan ohjelmiston arvioinnissa otettava huomioon molemmat ohjelmistot niitä käytettäessä.
  

## a) Asenna Linux virtuaalikoneeseen

### *Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

### Asennus
Aloitin tehtävän latamaalla koneelleni Virtualboxin (https://www.virtualbox.org/wiki/Downloads) sekä Debian Live -levykuvan (https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/.

Virtualboxin asennus sujui nopeasti ja sovelluksen avattuani pääsin luomaan virtuaalikoneen. Virtuaalikoneen luominen alkoi kohdasta "New", jonka jälkeen avautui "Create Virtual Machine" -ikkuna. Siirryin ikkunan alareunasta Expert Modeen, ja aloin täyttämään tarvittavia tietoja. Näihin tietoihin lukeutui mm. nimitiedot ja käyttöjärjestelmä sekä laitteistoon ja kovalevyyn liittyvät asetukset. 
<img width="682" alt="Linux3" src="https://github.com/user-attachments/assets/d9889d02-eb77-49dd-a19e-359a2ba66685">
<img width="680" alt="Linux4" src="https://github.com/user-attachments/assets/5ebbb98d-8ca7-4f26-b8a1-ef51496bd121">
<img width="680" alt="Linux5" src="https://github.com/user-attachments/assets/eb94d394-aee0-4c97-b6a9-d49290f06c87">
<img width="676" alt="Linux6" src="https://github.com/user-attachments/assets/ec517c62-d625-498a-bc63-142d29f4178a">
Kun olin täyttänyt tarvittavat tiedot, loin virtuaalikoneen klikkaamalla painiketta "Finish".

Seuraavaksi siirryin "Settings" -kohtaan Virtualbox Managerin kautta  ja valitsin kohdan "Storage". Valitsin "Empty" CD-levyn ja edelleen kohasta "Attributes" painoin uudestaan CD-levyä. Tähän kohtaan valitsin "debian-live..." -tiedoston ja klikkasin sen jälkeen kohdasta "OK" hyväksyäkseni muutokset.
<img width="779" alt="Linux18" src="https://github.com/user-attachments/assets/6fe406a8-1da3-4733-a49b-e7d23bd31aad">
<img width="664" alt="Linux2" src="https://github.com/user-attachments/assets/89501509-ac6a-4859-a17f-48af9e25d920">


### Käynnistys

Asennuksen jälkeen siirryin virtuaalikoneeni käynnistysvaiheeseen. Virtuaalikoneen käynnistäminen tapahtui painamalla kohtaa "Start". Ruudulle avautuvasta "Boot Menu" -kohdasta valitsin "Live system (amd64)" vaihtoehdon. Valinnan jälkeen pääsin ensimmäistä kertaa Linuxini työpöydälle. 

<img width="316" alt="Linux7" src="https://github.com/user-attachments/assets/3bd34c65-4d81-4f29-bcf3-954e73d88738">
<img width="554" alt="Linux8" src="https://github.com/user-attachments/assets/7455891a-37b2-4d46-87c2-290c5c1c3b8e">

Ensimmäisenä Linuxissa testasin sen toimivuutta selaimessa. Hakusanaksi selaimeen valitsin "Koira" ja se tuottikin onnistuneen lopputuloksen.

<img width="410" alt="Linux9" src="https://github.com/user-attachments/assets/2c903cc4-23c0-449e-8757-d9e9ccbc07e0">

Seuraavaksi siirryin asentamaan Debianin klikkaamalla "Install Debian" -kuvaketta:
"Welcome" -kohdasta valitsin kieleksi englanti.

<img width="416" alt="Linux10" src="https://github.com/user-attachments/assets/11db03c7-cbe2-4d0e-85e9-aadf31125918">

"Location" -kohdasta valitsin "Helsinki".

<img width="414" alt="Linux11" src="https://github.com/user-attachments/assets/b59afaa7-1070-469d-8a48-5f6baa3e3e98">

"Keyboard" -kohdasta "Generic 105-key PC"; "Finnish" ja "Default".

<img width="412" alt="Linux12" src="https://github.com/user-attachments/assets/cf7b1ed5-685f-451a-a995-18dc38737e75">

"Partitions" -kohasta "Erase Disk".

<img width="410" alt="Linux13" src="https://github.com/user-attachments/assets/e8bebb67-c8b2-44d8-8f6b-0c3a686828fe">

"Users" -kohassa täytin nimitiedot itsestäni ja koneesta sekä valitsin käyttäjälleni salasanan. 

<img width="415" alt="Linux14" src="https://github.com/user-attachments/assets/81b523cd-f8e0-4a72-bd4b-5965024713e2">

Tämän jälkeen ruudulle ilmestyi sisäänkirjautuminen, jossa aikaisemmin täyttämilläni tiedoilla pääsin kirjautumaan sisälle ja takaisin työpöydälleni.

<img width="403" alt="Linux17" src="https://github.com/user-attachments/assets/b8c4e358-550c-4a42-a665-3cc19cd2d82e">

<img width="452" alt="Linux16" src="https://github.com/user-attachments/assets/942480ad-ce58-40f2-8583-b7d85a37d242">


# Lähteet
Karvinen, Tero. 21.8.2024. Oppitunti. Linux Palvelimet.

Karvinen, Tero. 2023. Install Debian on Virtualbox. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/
