# h4 Maailma kuulee

## x) Lue ja tiivistä

### Teoriasta käytäntöön pilvipalvelimen avulla

https://susannalehto.fi/2022/teoriasta-kaytantoon-pilvipalvelimen-avulla-h4/

- Ei vuokrata vain palvelinta, vaan myös domain nimi palveluntarjoalta
- Suojataan palvelin palomuurilla. Ensin reikä ssh-palvelimelle!
- Asenetaan apache-weppipalvelin
- Päivitetään palvelimen kaikki ohjelmat

### First Steps on a New Virtual Private Server - an Example on DigitalOcean

https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

- Hyvät salasanat!
- Älä jumita vanhassa, vaan päivitä paketit!
- Yksinkertaista

## Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

## a) Vuokraa oma virtuaalipalvelin

Apuna vuokrauksessa Teron ohjeet: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/

14.9.2024 lähdin vuokraamaan palvelinta GitHub Educationin kautta. GitHub Educationin sivuilta siirryin linkin kautta DigitalOceanin sivuille ja kirjauduin isään käyttäen GitHub:in tunnuksia. Rekisteröintiin vaadittiin maksukortin tiedot ja se onnistui ongelmitta. Siirryin sivun vasemmasta laidasta kohtaan "Billing", mutta jostain syystä sieltä puuttui GitHub Educationin Student Pack. Siispä jouduin erikseen lähteä tekemään hakemusta Student Packin saamiseksi GitHub Educationin sivulta.

Hakemuksen teon aloitin käymällä läpi alla näkyvät ohjeet:

![Screenshot 2024-09-16 200310](https://github.com/user-attachments/assets/de55bd75-727d-47da-87ae-898984143203)

GitHubin asetusten muuttamisen jälkeen pääsin lähettämään hakemuksen, joka hetkeä myöhemmin hyväksyttiin:

![Screenshot 2024-09-16 195457](https://github.com/user-attachments/assets/a8963d0e-b6bb-4e22-aaf6-ce79598854f5)

Odotin Student Packin astuvan voimaan miltein heti, mutta todellisuudessa siihen olisi kulunut useampi päivä. Vielä 16.9. en ollut saanut kyseistä pakettia, joten jouduin tyytymään DigitalOceanin omaan tarjoukseen ($200 credittiä, 60pv). 

16.9. klo 20:25 aloin vihdoin vuokraamaan virtuaalipalvelimen sivun ylälaidasta kohdasta "Create" ja "Droplet". Asetuksiksi valikoitui seuraavat:
- Region: Frankfurt
- Image: Debian 12 x64
- Size: Basic
- CPU: Regular SSD, $6/kk, 1GB prosessori, 25GB kovalevy, 1000GB siirtodata
- Password: vahva salasana
- Name: pilvinen

Klo 20:33 valmis tuotos tuli näkyviin kohtaan "First Project":

![Screenshot 2024-09-16 203307](https://github.com/user-attachments/assets/64a7ebc1-38ba-47ea-ba3d-7baecb062182)

## b) Alkutoimet virtuaalipalvelimella

16.9. klo 20:40

Onnistuneen palvelimen vuokrauksen jälkeen siirryin suorittamaan virtuaalipalvelimen alkutoimia. 

Kokeilin terminaalissa ottaa ssh-yhteyden komennolla $ ssh root@206.189.49.237, mutta kometoa ei löytynyt. Siispä asensin ssh:n komennolla $ sudo apt-get -y install ssh. Asennus meni läpi ja pääsin jatkamaan.

![Screenshot 2024-09-17 154700](https://github.com/user-attachments/assets/e0932c2a-a8b4-4777-a0f9-1d8f011d808c)

![Screenshot 2024-09-17 154808](https://github.com/user-attachments/assets/4c0396ee-333f-48d4-b924-a5a0e9c5bd4e)

klo 20.45

Seuraavaksi hain ja suoritin päivitykset komennolla $ sudo apt-get update ja $ sudo apt-get upgrade. Päivitysten jälkeen siirryin asentamaan palomuurin komennolla $ sudo apt-get install ufw. Tein myös ssh:lle reiän komennolla $ sudo ufw allow 22/tcp sekä laitoin palomuurin päälle komennolla $ sudo ufw enable.

![Screenshot 2024-09-17 155335](https://github.com/user-attachments/assets/b30de742-0e1f-4be8-93f7-236d81ad7779)

![Screenshot 2024-09-17 155434](https://github.com/user-attachments/assets/349269df-ecbd-483a-bc45-fd23890b2975)

![Screenshot 2024-09-17 155621](https://github.com/user-attachments/assets/9e1fc841-e4b4-4387-b3cd-66ef5be35351)

![Screenshot 2024-09-17 155720](https://github.com/user-attachments/assets/8aedbc62-e5b2-43eb-babf-c4a52b354ed0)

Klo 20.55

Seuraavaksi siirryin luomaan käyttäjätunnuksen komennolla $ sudo adduser siiri

![Screenshot 2024-09-17 155804](https://github.com/user-attachments/assets/a8d479fd-3162-4232-8818-b6d919ae25a8)

Ja heti perään tein käyttäjästä sudokäyttäjän komennolla $ sudo adduser siiri sudo sekä testasin uusien tunnuksien toimivuutta toisessa terminaalissa komennolla $ ssh siiri@206.189.49.237

![Screenshot 2024-09-17 160753](https://github.com/user-attachments/assets/a84a5f4d-30b4-4b20-9c40-54e55ae5bad6)

Ja sehän onnistui hienosti! Onnistuneen testauksen jälkeen suljin root-käyttäjäni komennolla $sudo usermod --lock root. Poistin myös käytöstä root sisäänkirjautumisen ssh:ssa komennolla /etc/ssh/sshd_config -> PermitRootLogin Yes -> No. Ja lopuksi vielä käynnistin uudelleen ssh:n, jotta asetukset astuvat voimaan komennolla $ sudo service ssh restart.

Klo 21.15

Valmista tuli!

## c) Asenna weppipalvelin omalle virtuaalipalvelimelle

17.9. klo 15.30

Aloitin ottamalla ssh-yhteyden virtuaalipalvelimeen käyttäjätunnuksillani komennolla $ ssh siiri@206.189.49.237.

![Screenshot 2024-09-17 162824](https://github.com/user-attachments/assets/cad3ea6e-b21e-4bdb-85ce-62802757aa2b)

Sen jälkeen asensin apache2:n komennolla $ sudo apt-get -y install apache2.

![Screenshot 2024-09-17 170657](https://github.com/user-attachments/assets/90e0a473-56d6-40f4-9217-f87771ee0753)

Ja vielä tein reiän palomuurin porttiin komennolla $ sudo ufw allow 80/tcp.

![Screenshot 2024-09-17 162904](https://github.com/user-attachments/assets/121bbf9d-80f2-49af-8bd6-ea8bb97bf48a)

Klo 15.50 

Webbiselain auki ja testaus. Onnistuiko? Onnistui.

![Screenshot 2024-09-17 170501](https://github.com/user-attachments/assets/6b0b2f7d-65be-4f46-83c0-5dd720d7ee7e)

## Lähteet

Karvinen, Tero. 11.9.2024. Oppitunti. Linux Palvelimet. 

Tehtävänanto. Karvinen, Tero. Linux Palvelimet 2024 alkusyksy. 2022. Luettavissa: https://terokarvinen.com/linux-palvelimet/

Karvinen, Tero. 2012. First Steps on a New Virtual Private Server - an Example on DigitalOcean and Ubuntu 1.04 LTS. Luettavissa: https://terokarvinen.com/2017/first-steps-on-a-new-virtual-private-server-an-example-on-digitalocean/
