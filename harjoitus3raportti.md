# Harjoitus H3

Linkki tehtävänantoon [tästä](http://terokarvinen.com/2020/configuration-management-systems-palvelinten-hallinta-ict4tn022-autumn-2020/#h3-versionhallinta)

Tehtävä suoritettiin 16.11.2020 VirtualBoxin kautta Xubuntu 18.04.5 LTS:llä. Koneessa on jo valmiiksi asennetut salt master sekä slave.

### a) MarkDown. Tee tämän tehtävän raportti MarkDownina.

Aloitin tehtävän luomalla GitHub -tunnuksen sekä sinne uuden repositoryn *palvelintenhallintah3*. Seurasin tässä vaiheessa [Tero Karvisen ohjetta.](http://terokarvinen.com/2016/publish-your-project-with-github/)
Seuraavaksi ajoin seuraavat komennot järjestyksessä:

```$ sudo apt-get update
$ sudo apt-get -y install git
(asennus)
$ git config --global user.email "atro.lindell@myy.haaga-helia.fi"
$ git config --global user.name "Atro Lindell"
(kertoo gitille nimen sekä sähköpostiosoitteen)
$ git config --global credential.helper "cache --timeout=3600"
(muistiasetus salasanalle)
$ git clone https://github.com/Astrob0e/palvelintenhallintah3.git
(repon kloonaus GitHubista harjoituskoneelle)
```

Ensikäytön yhteydessä synkronoin kloonin muutoksille komennolla

  `$ git add . && git commit; git pull && git push`

Tätä komentoa käytin tästä eteenpäin joka kerta, kun halusin synkronoida tekemäni muutokset.
 
Koska tässä tehtävänannossa pyydettiin palauttamaan raportti MarkDownina, loin nano -tekstieditorin avulla  kansioon *~/palvelintenhallintaharjoitus3* tiedoston *harjoitus3raportti.md*, johon kirjoitin raporttini.

![1]

MarkDownin opettelu sujui melko vaivattomasti [MarkDown -käyttöohjeen](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
 avulla. Tein ensimmäiset muokkaukseni MarkDown -tiedostoon, jonka jälkeen suljin ja tallensin muutokseni. Nämä eivät kuitenkaan vielä näkyneet GitHub -sivullani, vaan ensin muutokset täytyi synkronoida aikaisemmin mainitulla `$ git add . && git commit; git pull && git push` -komennolla ja commit -viestiksi kirjoitin "add h3":

![2]  ![3]

Tämän jälkeen harjoitusraporttini ilmestyi sisältöineen GitHub -sivulleni niin kuin pitikin:

![4]

### d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

`git log` -komennon avulla voidaan tulostaa commit -historia:

![5]

`git diff` -komento puolestaan näyttää, mitä eroja tiedostoissa löytyy työskentelytilassa olevalla kloonilla verrattuna GitHubin versioon (muutokset, joita ei vielä commitattu):

![6]

`git blame <halutun tiedoston nimi>` -komennolla kyetään osoittamaan se taho, joka on vastuussa kustakin tehdystä muutoksesta:

![7]
 

### e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

Tässä kohtaa ripottelin ylimääräisiä merkkejä ja symboleja sekä kirjoitusvirheitä kaikkialle harjoitusraporttiini. Niiden manuaalisesti poistaminen olisi ollut kovin työlästä, joten `git reset --hard` -komennolla pystyin palaamaan edelliseen toimivaan versioon, jossa tätä ongelmaa ei esiintynyt:

![8]

![9]

![10]
  
### f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman.

Tässä tehtävässä halusin asentaa koneelle Terminator -nimisen terminaaliemulaattorin. Asensin ohjelman ensin manuaalisesti:

```
$ sudo apt-get update
$ sudo apt-get install terminator
```
![11]

![12]

Seuraavaksi poistin Terminatorin komennolla:
  `$ sudo apt-get purge terminator`

Todettuani, että asennus onnistuu moitteetta manuaalisesti pystyin hyvillä mielin siirtymään automaatiovaiheeseen. Ensin kokeilin, toimiiko aiemmin luomani minion vielä oikein komennolla `$ sudo salt '*' cmd.run 'whoami'`

Sitten loin polkuun */srv/salt* kansion */terminator*, jonne loin *init.sls* -tiedoston. Tätä tiedostoa muokkasin komennolla `sudoedit`. Määritin asetukseksi sen, että tilaa kutsuessa jokainen minion asentaa ohjelman automaattisesti:
  
![13]

![14]

Enää olikin jäljellä vain tilan käyttöönotto sekä toiminnan testaus. Otin tilan käyttöön komennolla
  `$ sudo salt '*' state.apply terminator`

Ja tämän jälkeen varmistin vielä, että ohjelma löytyy koneelta:

![15]

![16]

Ja siinäpä se:)
## Lähteet:

http://terokarvinen.com/2020/configuration-management-systems-palvelinten-hallinta-ict4tn022-autumn-2020/#h3-versionhallinta

http://terokarvinen.com/2016/publish-your-project-with-github/

https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet


[1]: https://i.gyazo.com/5a600f49d4f61629cbce1c1910b6eb3e.png "1"

[2]: https://i.gyazo.com/568b7c8a41b980f2f475c353ecb35470.png "2"

[3]: https://i.gyazo.com/82086cc3840e804dc0bc5e39207c8f8f.png "3"

[4]: https://i.gyazo.com/c4749365a80699eae701f1161e401e82.png "4"

[5]: https://i.gyazo.com/08d5e662bc0c99460f6c8c23297a35a5.png "5"

[6]: https://i.gyazo.com/042977d84177c8015f786d4d77076237.png "6"

[7]: https://i.gyazo.com/842bd75c512bc629453dd77bf5cf7f33.png "7"

[8]: https://i.gyazo.com/88295aca5c86bde3f1dadd25afd97071.png "8"

[9]: https://i.gyazo.com/e96e3578701d1a4cc907d5dc940edebc.png "9"

[10]: https://i.gyazo.com/0c49c93c7300319d07114cb6f9ac54e2.png "10"

[11]: https://i.gyazo.com/809109a6b3b6f9398cd27e485cbae5cf.png "11"

[12]: https://i.gyazo.com/37070f26722bf10932b7750820c03179.png "12"

[13]: https://i.gyazo.com/3b37f5aa0a1c8160e39a608cace235c1.png "13"

[14]: https://i.gyazo.com/fd90433890500f719cb0417c60fac8f5.png "14"

[15]: https://i.gyazo.com/b630dc088a23359ec9c019d206140f75.png "15"

[16]: https://i.gyazo.com/2fc9dc1249d530240423895d82ecd7c7.png "16"

