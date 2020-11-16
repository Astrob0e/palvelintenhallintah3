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

![2]

MarkDownin opettelu sujui melko vaivattomasti [MarkDown -käyttöohjeen](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
 avulla. Tein ensimmäiset muokkaukseni MarkDown -tiedostoon, jonka jälkeen suljin ja tallensin muutokseni. Nämä eivät kuitenkaan vielä näkyneet GitHub -sivullani, vaan ensin muutokset täytyi synkronoida aikaisemmin mainitulla `$ git add . && git commit; git pull && git push` -komennolla:
### d) Näytä omalla git-varastollasi esimerkit komennoista ‘git log’, ‘git diff’ ja ‘git blame’. Selitä tulokset.

### e) Tee tyhmä muutos gittiin, älä tee commit:tia. Tuhoa huonot muutokset ‘git reset –hard’. Huomaa, että tässä toiminnossa ei ole peruutusnappia.

### f) Tee uusi salt-moduli. Voit asentaa ja konfiguroida minkä vain uuden ohjelman: demonin, työpöytäohjelman tai komentokehotteesta toimivan ohjelman.

## Lähteet:

http://terokarvinen.com/2020/configuration-management-systems-palvelinten-hallinta-ict4tn022-autumn-2020/#h3-versionhallinta

http://terokarvinen.com/2016/publish-your-project-with-github/

https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

[1]:

[2]: https://i.gyazo.com/5a600f49d4f61629cbce1c1910b6eb3e.png "2"

[3]:  "3"

[4]:

[5]:

[6]:

[7]:


