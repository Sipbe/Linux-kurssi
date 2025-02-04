# h3 - Hello Web Server

## x) Lue ja tiivistä

### Name-based Virtual Host Support 
(Apache HTTP server ptoject, n.d.)

- IP-perusteiset virtuaali hostit tarvitsevat eri IP-osoitteen jokaista hostia kohden
- Nimiperusteiset virtuaalihostit eivät tarvitse useaa IP-osoitetta, vaan useat eri hostit voivat jakaa saman IP-osoitteen
- Virtual hostin luomisen tulee sisältää ainakin ServerName sekä DocumentRoot
- Hostname yhdistetään oikeaan IP-osoitteeseen DNS palvelimen avulla

###  Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address
(Karvinen, 10.4.2018)

- Apache mahdollistaa mnta domainia yhdellä IP-osoitteella
- Apache asennetaan komennolla $ sudo apt-get -y install apache2
- Palvelimen luomiseen käyetetään sudo-kometoja ja sitä testataan curl-komennoilla

## Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor

## a) Localhost testaus

Aloitin Apache2:n asennuksen tutustumalla siihen liittyviin ohjeistuksiin. Löysinkin netistä asenukseen ohjeistuksen (https://reintech.io/blog/installing-apache-on-debian-12-step-by-step-guide), jonka pohjalta tein asennuksen. Apache2:n asennus sujui mutkattomasti ja testasin myös, että se on toiminnassa. Apache2:n asennukseen käytin seuraavaa komentoa:

#### sudo apt-get -y install apache2

![Screenshot 2024-09-09 200452](https://github.com/user-attachments/assets/a9f503af-6a3c-40b6-a044-bffb943d6cea)

![Screenshot 2024-09-08 180112](https://github.com/user-attachments/assets/b1690df8-a551-4209-9754-6ae45f99336d)

Seuraavaksi siirryin selaimella katsomaan, miltä localhost näyttää ja tässä tulos:

![Screenshot 2025-02-04 184652](https://github.com/user-attachments/assets/3f9856ec-9b36-45e7-a45f-6c25eb4dbf9f)

## b) Lokin rivit

Seuraavaksi siirryin lokien pariin ja suoritin komennot:

#### sudo tail /var/log/apache2/acces.log
sekä
#### sudo tail /var/log/apache2/error.log

Näillä kyseisillä komennoilla oli tarkoitus tutkia lokia. 

Access.log:
![Screenshot 2025-02-04 190929](https://github.com/user-attachments/assets/7dccc8ff-2e08-4bce-9ee4-77806053e441)

Access. log tallentaa kaikki HTTP-pyynöt, jotka verkkopalvelin vastaanottaa. Access.Log:in jokainen rivi noudattaa seuraavanlaista kaavaa:
#### IP_ADDRESS - [DATE & TIME] "REQUEST_METHOD RESOURCE HTTP_VERSION" STATUS_CODE RESPONSE_SIZE "REFERRER" "USER AGENT"

Access.log kertoo seuraavat asiat:
- Kuka vierailee sivustolla
- Mitä tiedostoja/sivuja pyydetään
- Milloin pyyntö on tapahtunut
- Miten pyyntö käsiteltiin
- Kuinka paljon dataa palvelin lähetti vastauksena
- Mistä selainohjelmas pyyntö tehtiin

Error.log:
![Screenshot 2025-02-04 191031](https://github.com/user-attachments/assets/15abd556-4f9c-4a0e-8918-5d05a3ec0e2b)

Error.log tallentaa palvelimen virheet ja varoitukset. Se auttaa selvittämään miksi sivusto ei toimi. Error.log:in jokainen rivi noudatta seuraavanlaista kaavaa:
#### [TIMESTAMP] [LOG_LEVEL] [PROCESS_ID:THREAD_ID] MESSAGE
Merkintä kertoo siis 1. Virheen aikaleiman 2. Virheen vakavuuden 3. Apache-moduulin nimen 4. Prosessin tunnuksen 5. Virhekoodin 6. Virheilmoituksen selityksen

## c) Etusivu uusiksi

Poistetaan oletusarvoinen virtual host käytöstä komennolla
#### sudo a2dissite 000-default.conf

![Screenshot 2025-02-04 144354](https://github.com/user-attachments/assets/d81c1f97-9ecc-40a7-b3c0-9de0d17d83f5)

Luodaan uusi hakemisto sivustolle komennolla
#### sudo mkdir -p /var/www/hattu.example.com

... ja asetetaan luvat komennoilla
#### sudo chown -R www-data:www-data /var/www/hattu.example.com
### sudo chmod -R 755 /var/www/hattu.example.com

![Screenshot 2025-02-04 144415](https://github.com/user-attachments/assets/553f155f-efe3-4241-8748-c1b1fcbd7769)

Luodaan virtual hostin konfiguraatiotiedosto komennolla
#### sudo nano /etc/apache2/sites-available/hattu.example.com.conf

![Screenshot 2025-02-04 144432](https://github.com/user-attachments/assets/2aad6c89-8156-4c90-a4d6-550a1fc743cc)

Otetaan uusi virtual host käyttöön komennolla
#### sudo a2ensite hattu.example.com.conf

... ja 
#### sudo systemctl restart apache2

![Screenshot 2025-02-04 144452](https://github.com/user-attachments/assets/2c723744-1816-44a1-bc2c-ddd97965115f)

Lisätään testisivu komennolla
#### echo "<h1>Welcome to hattu.example.com</h1>" | sudo tee /var/www/hattu.example.com/index.html

![Screenshot 2025-02-04 144544](https://github.com/user-attachments/assets/5b9fdd92-0e23-4816-8210-e7b8e717cee1)

Testataan selaimella osoitetta
#### http://hattu.example.com

![Screenshot 2025-02-04 144206](https://github.com/user-attachments/assets/43f8a2f9-4467-4664-b10e-f2980f987926)

## d) Validi HTML5 sivu

Siirrytään sivuston hakemistoon komennolla
#### cd /var/www/hattu.example.com

![Screenshot 2025-02-04 151042](https://github.com/user-attachments/assets/f3a1d5e9-caf4-4f51-a3f6-ad9a991ab24b)

Luodaan index.html-tiedosto komennolla
#### sudo nano index.html

![Screenshot 2025-02-04 151053](https://github.com/user-attachments/assets/24d9f1c0-88b7-43d8-9cbc-00038413c91f)

Lisätään HTML5-koodia

![Screenshot 2025-02-04 151141](https://github.com/user-attachments/assets/19354ea9-a869-4b8b-a559-82701bcc618d)

Lisätään CSS-tiedosto komennolla
#### sudo nano /var/www/hattu.example.com/style.css

![Screenshot 2025-02-04 151201](https://github.com/user-attachments/assets/391e7d1e-7aec-4763-8c1e-ad44540d4dcd)

![Screenshot 2025-02-04 151235](https://github.com/user-attachments/assets/7d1da30a-944a-4dac-8d03-120493d7a4ba)

Käynnistetään Apache uudelleen komennolla
#### sudo systemctl restart apache2

Tarkistetaan miltä sivustolla http://hattu.example.com näyttää

![Screenshot 2025-02-04 151335](https://github.com/user-attachments/assets/bc7e796b-d29d-4081-aecd-cebc8c8d9005)


## e) 'curl -I' -ja 'curl' -komennot

'curl' -komento näyttää peruskäytössä verkkosivun sisällön, mutta sillä voidaan myös lähettää HTTP-pyyntöjä ja ladata tiedostoja verkosta.
#### esimerkissä käytetty curl localhost

![Screenshot 2025-02-04 151520](https://github.com/user-attachments/assets/d10129b8-3fa6-4a29-8f5d-282a5c8359fc)

'curl -I' -komento lähettää HTTP-pyynnön palvelimelle ja näyttää vain HTTP-otsakkeet. Komennolla voidaan tarkistaa onko palvelin toiminnassa, mikä on HTTP-vastauskoodi, mitä palvelinteknologiaa käytetään, onko uudelleenohjauksia ja millainen välimuistikäytäntö palvelimella on.
#### esimerkissä käytetty curl -I localhost

![Screenshot 2025-02-04 151609](https://github.com/user-attachments/assets/44adb3ca-2540-400d-9dfe-72f6ced225c2)

## Lähteet
Tehtävänanto. Karvinen, Tero. Linux Palvelimet 2025 alkukevät. 2022. Luettavissa: https://terokarvinen.com/linux-palvelimet/
Apache HTTP server ptoject. Name-based Virtual Host Support. n.d. Luettavissa: https://httpd.apache.org/docs/2.4/vhosts/name-based.html
Karvinen, Tero. Name Based Virtual Hosts on Apache – Multiple Websites to Single IP Address. 10.4.2018 https://terokarvinen.com/2018/04/10/name-based-virtual-hosts-on-apache-multiple-websites-to-single-ip-address/
