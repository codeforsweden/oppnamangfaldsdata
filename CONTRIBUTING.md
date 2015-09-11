Bidra till [öppenmångfaldsdata] (http://opendiversitydata.org/)
=======================

## Att Bidra

Det enklaste sättet att bidra med är att lämna in en fråga i [Github][issues].
Om du är intresserad av att bidra via pull begäran, läs vidare.

Alla data hanteras genom en serie [Yaml][yaml]-filerså det kan vara bra att läsa
upp på [Yaml syntax](http://docs.ansible.com/ansible/YAMLSyntax.html).

För att lägga till ett nytt företag, gå till [datafiler](_data/)och bekanta dig med
hur den är inställd. Det finns ett avsnitt och motsvarande fil för varje kategori och de alla följer detta
syntax:

### Riktlinjer

1. **Använd a Trevlig Ikon**: Ikonen måste vara 32x32 i storlek.

### Nya Företag

Värdena bör vara ganska rakt fram för att lägga till ett nytt företag. Matrisen för företag
`companies` bör redan vara definierat, lägg bara till ett nytt bolag för det som
detta exempel:

```yml
    companies:
        - name: Företagsnamn
          url: https://www.företag.com/
          twitter: FöretagsTwitter
          img: företagsikon.png
          data: Ja
          eeo-1: Ja
          date-updated: 201X
          documentation: <link to company's diversity data>
```

### Nya Industrier

För att lägga till en ny kategori / industri av företag, ändra värdet `industry` i [main.yml](_data/main.yml)
och följ mallen nedanför:

```yml
sections:
  - id: industry-id
    title: Industry Name
    icon: icon-class
```

#### Proffsråd

- Se Riktlinje #1 om ikoner. Png-filen borde gå i korresponderande mapp `img/section`.

- Av hänsyn till organisation och läsbarhet, är det uppskattat om du sätter nya företag i bokstavsordning och
att din bit om företaget följer samma ordning som i exemplet ovan.

- Om en webbplats inte har tillgängliga data, men det finns dokumentation som de arbetar på att släppa den och sedan använda:

  ```yml
  data: no
  status: <url to documentation>
  ```
  
### Andra Länder

Denna webbplats är inriktad på svenska företag, och vi söker efter standarddokumentformat för denna typ av data. Om Sverige har ett standardformat  som EEO-1, skicka in en fråga som vi kan använda platsen för att lägga till fler länder.

[yaml]: http://www.yaml.org/
[issues]: https://github.com/doubleunion/opendiversitydata/issues
