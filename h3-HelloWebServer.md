# h3 - Hello Web Server

## x) Lue ja tiivistä

### Name-based Virtual Host Support 
https://httpd.apache.org/docs/2.4/vhosts/name-based.html

- IP-perusteiset virtuaali hostit tarvitsevat eri IP-osoitteen jokaista hostia kohden
- Nimiperusteiset virtuaalihostit eivät tarvitse useaa IP-osoitetta, vaan useat eri hostit voivat jakaa saman IP-osoitteen
- Virtual hostin luomisen tulee sisältää ainakin ServerName sekä DocumentRoot
- Hostname yhdistetään oikeaan IP-osoitteeseen DNS palvelimen avulla

###  Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address
https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/

- Apache mahdollistaa mnta domainia yhdellä IP-osoitteella
- Apache asennetaan komennolla $ sudo apt-get -y install apache2
- Palvelimen luomiseen käyetetään sudo-kometoja ja sitä testataan curl-komennoilla

## Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

## a) Localhost testaus

Localhostin testaus ei tuottanut haluttua lopputulosta ei sitten millään. 

Aloitin Apache2:n asennuksen tutustumalla siihen liittyviin ohjeistuksiin. Löysnkin netistä asenukkseen ohjeistuksen (https://reintech.io/blog/installing-apache-on-debian-12-step-by-step-guide), jonka pohjalta tein asennuksen. Apache2:n asennus sujui mutkattomasti ja testasin myös, että se on toiminnassa. Tässä kohtaa kaikki vaikutti vielä olevan kuten pitääkin. Apache2:n asennukseen käytin seuraavaa komentoa:

#### sudo apt-get -y install apache2

![Screenshot 2024-09-09 200452](https://github.com/user-attachments/assets/a9f503af-6a3c-40b6-a044-bffb943d6cea)

![Screenshot 2024-09-08 180112](https://github.com/user-attachments/assets/b1690df8-a551-4209-9754-6ae45f99336d)

Kun menin katsomaan localhostiani, tuli ruudulle Apache Deafult pagen sijaan teksti "Forbidden...". 

![Screenshot 2024-09-09 203236](https://github.com/user-attachments/assets/41489ab5-a9d8-4b60-8d08-749eb7345101)

Lähdin selvittämään ongelmaa netistä löytyvien ohjeiden avulla, jotka olivat kuitenkin minulle hieman haastavia tulkita. Osoitteesta https://www.slingacademy.com/article/apache-forbidden-error-permission-denied/?utm_content=cmp-true löysin kuitekin selkeämmän ja vaiheittain ongelman ratkaisua selittävän ohjeen, jonka kolmea eri ratkaisuvaihtoehtoa lähdin testaamaan. Näiden ohjeiden mukaisesti kuitenkin kaikki näytti olevan kunnossa, eikä ratkaisua ongelmaani löytynyt kyseistä kautta.
Omat taitoni eivät siis riittäneet ratkaisemaan ongelmaa enkä löytänyt netistäkään selkeää vastausta ongelmaani. 

## b) Lokin rivit

Ongelmastani huolimatta päätin perehtyä myös osion muihin tehtäviin siltä osin kuin pystyin. Seuraavaksi suoritinkin komennot
#### sudo tail /var/log/apache2/acces.log
sekä
#### sudo tail /var/log/apache2/error.log

Näillä kyseisillä komennoilla oli tarkoitus tutkia lokia. 

![Screenshot 2024-09-08 181318](https://github.com/user-attachments/assets/2c267103-fe55-4ee4-993d-40df5157de97)

Ensimmäinen komento näyttää, että palvelinta on kutsuttu GET-pyynnöllä klo 18:02:45 8.9.2024.
Toinen komento puolestaan näyttää, onko palvelimella ollut virhetilanteita tai onko palvelimen toiminnassa ollut jotain normaalista poikkeavaa. Omassa tapauksessani kaikki näyttäisi olevan kunnossa lokin osalta.

## c) Etusivu uusiksi

Tässä osiossa en varsinaisesti saanut mitään aikaiseksi, ainakaan siihen pisteeseen, että ne olisivat oikeasti toimineet ja näkyneet palvelimella, mutta kokeilin silti suorittaa komentoja ja ymmärtää mitä ne tekevät ja miten ne toimivat.

![Screenshot 2024-09-08 185716](https://github.com/user-attachments/assets/73a8e652-10d9-4f29-83ee-1909857c0aa7)

![Screenshot 2024-09-08 185820](https://github.com/user-attachments/assets/804ecdc5-78e8-4af3-8288-be322087eea2)

![Screenshot 2024-09-08 190005](https://github.com/user-attachments/assets/d65196ca-3ff3-45ba-8d6d-f806fff79bd3)

![Screenshot 2024-09-08 190349](https://github.com/user-attachments/assets/e7c42e3d-da28-4934-b542-8f1f7cc9e927)

## d) Validi HTML5 sivu

## - - -

## e) 'curl -I' -ja 'curl' -komennot

'curl' -komento näyttää verkkosivulta saadun html-sivun:
#### esimerkissä käytetty curl localhost

![Screenshot 2024-09-09 210125](https://github.com/user-attachments/assets/f2709334-652e-4810-81b6-b59b9cfab0e8)

'curl -I' -komento näyttää vain verkkosivuston HEADit:
#### esimerkissä käytetty curl -I localhost

![Screenshot 2024-09-09 210228](https://github.com/user-attachments/assets/e241c691-c0d0-4a02-b82c-4b7d6f356fcc)

## Lähteet
Tehtävänanto. Karvinen, Tero. Linux Palvelimet 2024 alkusyksy. 2022. Luettavissa:https://terokarvinen.com/linux-palvelimet/ 
