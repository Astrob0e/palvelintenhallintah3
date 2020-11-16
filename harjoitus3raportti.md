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


 

### e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

### f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman.

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

[7]: "7"

[8]: "8"

[9]: "9"

[10]: "10"

