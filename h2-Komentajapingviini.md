# h2 - Komentaja Pingviini

## x) Lue ja tiivistä

### Command Line Basics Revisited
https://terokarvinen.com/2020/command-line-basics-revisited/?fromSearch=command%20line%20basics%20revisited

- Linuxin komentorivi on syntynyt jopa ennen internettiä ja se on jokapäiväiseen käyttöön erinomainen
- Linuxin komentoriviä kuvaillaan käteväksi, nopeaksi, ilmeikkääksi sekä helpoksi automatisoida
- Pääasiassa Linuxin komentorivissä pärjää muutamilla komennoilla, jotka on hyvä opetella ulkoa
- Yleisimpiä liikkumiseen käytetettäviä komennot ovat mm. "pwd", "ls" sekä "cd..."
- SSH mahdollistaa etäkäytön, jolla voidaan ottaa salattu yhteys järjestelmästä toiseen
- Tiedostojen etsimiseen Linuxissa käytetään vain muutamaa komentoa, jotka ovat samat kaikissa Linuxin järjestelmissä

## Koneen tiedot
- Device: X1 Carbon 5th Gen - Kabylake (Type 20HR, 20HQ) Laptop (ThinkPad) - Type 20HQ
- Serial Number: PF105Q96
- Processor:	Intel(R) Core(TM) i5-7300U CPU @ 2.60GHz   2.71 GHz
- Installed RAM:	8,00 GB (7,84 GB usable)
- Storage: 237GB
- System type:	64-bit operating system, x64-based processor
- Bios Version: N1MET37W 1.22

## Komentorivi-harjoitusten aloitus

Tehtävänanto: https://terokarvinen.com/linux-palvelimet/

Aloitin harjoitus 2:n käynnistämällä edellisessä tehtävässä luodun virtuaalikoneen. Sen jälkeen siirryin käyttöjärjestelmästä jo valmiiksi löytyvään terminaaliohjelmaan. Ensimmäisenä päivitin pakettilistan, jotta järjetelmä on varmasti ajan tasalla. Pakettilistan päivityksen tein komennolla:

#### $ sudo apt-get update

![Linux19](https://github.com/user-attachments/assets/b43357b5-8951-483c-9c75-dc63a3c7f0d1)

## a) Micro

Pakettilistan päivityksen jälkeen siirryin suorittamaan Micron asennuksen. Kyseinen asennus vei vain muutamia sekunteja ja asennuksen suorittamiseen käytin seuraavaa komentoa: 

#### $ sudo apt-get -y install micro

<img width="277" alt="Linux20" src="https://github.com/user-attachments/assets/4d971624-fc42-4913-8d3a-c7d2fec65c4a">

## b) Apt

Seuraavaksi sain valita kolme itselle entuudestaan vierasta komentoriviohjelmaa. Päätin kokeilla asentaa kaikki kolme ohjelmaa samalla kertaa yhdellä komennolla. Ohjelmiksi valikoituivat Figlet, CMatrix sekä Aafire. Näiden kolmen ohjelman saman aikaiseen asentamiseen käytin komentoa:

#### $ sudo apt-get -y install libaa-bin cmatrix figlet

Komennon avulla asennus onnistui ja asennetut ohjelmat näyttivät seuraavanlaisilta:

### Figlet

![Screenshot 2024-09-03 173240](https://github.com/user-attachments/assets/5dc5b136-55e1-4677-a657-8781decf8371)

### CMatrix

![Screenshot 2024-09-03 173420](https://github.com/user-attachments/assets/8a4b6fc9-f623-4d23-8a55-79e8027dcb3e)

### Aafire

![Screenshot 2024-09-03 174231](https://github.com/user-attachments/assets/23e796bd-8363-4067-9808-159f4b3c6b00)

Komentoriviohjelmat löytyivät sivustolta: https://www.tecmint.com

## c) FHS

Seuraavaksi siirryin kansioiden pariin. 

Kansioiden esittelyn suoritin seuraavilla komennoilla:

#### $ ls /

![Screenshot 2024-09-03 164854](https://github.com/user-attachments/assets/62019db2-755f-488a-b5fb-338aa7c2c130)

Tuloksena lista kaikista kansioista.

#### $ ls /home

![Screenshot 2024-09-03 165452](https://github.com/user-attachments/assets/5ba4d752-a4e1-439e-b691-75f4d0e91942)

Tuloksena home-hakemistot.

#### $ ls /home/siival

![Screenshot 2024-09-03 165612](https://github.com/user-attachments/assets/09e21a36-bb61-451c-9f86-49f1ce377ca9)

Tuloksena henkilökohtaiset kansiot.

#### $ ls /etc

![Screenshot 2024-09-03 165748](https://github.com/user-attachments/assets/804b2c3d-3b74-4750-b754-feb2f2077f78)

![Screenshot 2024-09-03 165905](https://github.com/user-attachments/assets/fa8f0a87-b369-4c1e-9ded-723e08817747)

Tuloksena järjestelmän asetukset.

#### $ ls /media

Tuloksena media. Omalla kohdalla tämä oli tyhjä.

#### $ ls /var/log

![Screenshot 2024-09-03 170151](https://github.com/user-attachments/assets/e304e216-62b2-4ea4-b6be-61ccd1266d6a)

Tuloksena lokitiedot.

## d) The Friendly M

Seuraavaksi pääsin testaamaan Grep-komentoa. Grep-komennolla etsitään ja käsitellään tiedostojen tekstejä.

Grep-komennon toimintaa testasin seuraavilla komennoilla:

#### $ grep "Kissa" kissa.txt

![Screenshot 2024-09-03 171326](https://github.com/user-attachments/assets/8a2050c6-b78f-4b07-b23e-0d5514544d60)

Kyseinen komento etsii tiedostosta "Kissa" -sanan.

#### grep -c "Kissa" kissa.txt

![Screenshot 2024-09-03 171338](https://github.com/user-attachments/assets/f37aa91e-e783-4b9a-86f7-1a98eda224e3)

Kyseinen komento esittää kuinka monta kertaa sana "Kissa" esiintyy tiedostoissa.

## e) Pipe

Pipen avulla yhdistellään erilaisia komentoja. Pipea kokeilin seuraavalla komennolla, joka listaa kaikki tiedostot ja hakemistot 'more' komennon syötteeksi:

#### $ ls -l | more

![Screenshot 2024-09-03 172305](https://github.com/user-attachments/assets/d2356e96-fa34-4c53-b21b-371d848474df)

## f) Rauta

Raudan listausta varten suoritettava komento

#### $ sudo lshw -short -sanitize

ei toiminut, vaan terminaaliin tuli vastaus "sudo: lshw: command not found". Tätä varten minun oli asennettva lshw seuraavalla komennolla:

#### $ sudo apt-get -y install lshw

![Screenshot 2024-09-03 163229](https://github.com/user-attachments/assets/d0d2b17f-84e7-465c-a85d-60090ddf64b8)

<img width="338" alt="Linux22" src="https://github.com/user-attachments/assets/a0f5b228-ec38-482c-97a1-79a2597d04f7">

lshw:n asennuksessa kesti Micron tapaan muutama sekunti ja sen jälkeen aiemmin ilmestynyt "command not found" -ilmoitus ei enää toistunut, vaan sain raudan listattuna.

<img width="305" alt="Linux23" src="https://github.com/user-attachments/assets/b59a4910-2764-48d8-8db3-74ea83e9d034">

lshw on siis ohjelma, joka tekee yhteenvedon koneen osista. Yllä kuvattu lista on mielestäni kattava ja kertoo kaiken tarvittavan tiedon koneesta.


