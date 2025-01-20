# h1 - OMA LINUX

## x) Lue ja tiivistä

### Raportin kirjoittaminen
##### (Karvinen, Tero. 4.6.2006)
- Raportin tulee olla selkeä sekä helposti ymmärrettävissä ja toistettavissa
- On hyvä kertoa mikä onnistui, mikä ei onnistunut sekä miten ja missä ajassa testaaminen suoritettiin
- Raportissa tulee viitata lähteisiin 
- Raportin tulee olla todenmukainen ja aidosti omien tekojen ja ajatusten tuotos
### What is Free Software?
##### (GNU Operating System. 1.1.2024.)
- Vapaalla ohjelmistolla tarkoitetaan sellaista ohjelmistoa, joka ei suinkaan välttämättä ole arvoltaan ilmainen, mutta sen sijaan vapaasti mm. muokattavissa, kopioitavissa ja myytävissä. Vapaaseen ohjelmistoon pääsee käsiksi siis kuka tahansa ja jokaisella on vapaat kädet ohjelmiston käsittelyn suhteen.
- Jotta ohjelmistoa voidaan kutsua "vapaaksi ohjelmistoksi", on sen täytettävä riittävällä tasolla seuraavat neljä (4) vapautta:
  ##### 1) Vapaus suorittaa ohjelmaa haluamallaan tavalla haluamaansa tarkoitukseen.
  ##### 2) Vapaus opiskella, miten ohjelma toimii, ja muuttaa sitä niin, että se vastaa haluamaasi (pääsy lähdekoodiin).
  ##### 3) Vapaus levittää kopioita auttaakseen muita.
  ##### 4) Vapaus jakaa kopioita ohjelmiston muokatusta versiosta, jotta muut voivat hyötyä muutoksista (pääsy lähdekoodiin).
- Mikäli ohjelmistoon liittyy oleennaisesti toinen toiminnallisuutta täydentävä ohjelmisto, on vapaan ohjelmiston arvioinnissa otettava huomioon molemmat ohjelmistot niitä käytettäessä.
  

## a) Asenna Linux virtuaalikoneeseen

### Koneen tiedot
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

<img width="399" alt="Linux2" src="https://github.com/user-attachments/assets/fab3ea74-d55c-413a-b2b7-ce662cae2a51" />

Ensimmäisenä Linuxissa testasin sen toimivuutta selaimessa. Hakusanaksi selaimeen valitsin "Koira" ja se tuottikin onnistuneen lopputuloksen.

<img width="410" alt="Linux9" src="https://github.com/user-attachments/assets/01ec2803-9a65-45da-a1e1-ac42783bcfce" />

Seuraavaksi siirryin asentamaan Debianin klikkaamalla "Install Debian" -kuvaketta:
"Welcome" -kohdasta valitsin kieleksi englanti.

<img width="413" alt="Linux10" src="https://github.com/user-attachments/assets/fee7f4be-24fd-4936-8201-ce9c5f370579" />

"Location" -kohdasta valitsin "Helsinki".

<img width="411" alt="Linux11" src="https://github.com/user-attachments/assets/9d6ec5b0-74a6-46d0-ba9b-4de20a71929e" />

"Keyboard" -kohdasta "Generic 105-key PC"; "Finnish" ja "Default".

<img width="411" alt="Linux12" src="https://github.com/user-attachments/assets/4a1298ee-afb5-41d5-8a99-477dba0b6676" />

"Partitions" -kohasta "Erase Disk".

<img width="410" alt="Linux13" src="https://github.com/user-attachments/assets/e8bebb67-c8b2-44d8-8f6b-0c3a686828fe">

"Users" -kohassa täytin nimitiedot itsestäni ja koneesta sekä valitsin käyttäjälleni salasanan. 

<img width="413" alt="Linux14" src="https://github.com/user-attachments/assets/cc4272e9-be76-46bf-b0c0-63338794d930" />

Tämän jälkeen ruudulle ilmestyi sisäänkirjautuminen, jossa aikaisemmin täyttämilläni tiedoilla pääsin kirjautumaan sisälle ja takaisin työpöydälleni.

<img width="403" alt="Linux17" src="https://github.com/user-attachments/assets/b8c4e358-550c-4a42-a665-3cc19cd2d82e">

<img width="402" alt="Linux18" src="https://github.com/user-attachments/assets/b6e8bbb5-f6f8-491e-81f3-82e9a1760897" />

# Lähteet
Karvinen, Tero. 14.1.2025. Oppitunti. Linux Palvelimet.

Karvinen, Tero. 4.6.2006. Raportin kirjoittaminen. Luettavissa: https://terokarvinen.com/2006/raportin-kirjoittaminen-4/

GNU Operating System. 1.1.2024. What is Free Software? Luettavissa: https://www.gnu.org/philosophy/free-sw.html

Karvinen, Tero. 2023. Install Debian on Virtualbox. Luettavissa: https://terokarvinen.com/2021/install-debian-on-virtualbox/
