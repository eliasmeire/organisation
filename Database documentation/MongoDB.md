# Database

## MongoDB

MongoDB is een open source document-georiënteerde database en is geschreven in C++. Er is geen schema, de documenten worden in de vorm van BSON (binair JSON) opgeslagen en de structuur van deze documenten is flexibel. De database kan gemakkelijk gedistribueerd worden, de data wordt dan over meerdere computers verspreid om gedistribueerde gegevensverwerking mogelijk te maken. MongoDB is geen relationeel databasemanagementsysteem, er is geen ondersteuning voor joins en voldoet ook niet aan de ACID-regels want de ondersteuning voor transacties is beperkt. MongoDB wordt gerekend tot de zogenaamde NoSQL-databases.

MongoDb is geschikt voor grote data het is schaalbaar en werk zonder relaties in tegenstelling tot bijvoorbeeld SQLite. Omdat we in ons project geen echte relaties nodig hebben is de keuze daarom ook makkelijk gemaakt voor MongoDB.

### Voorbeeld eventuele database structuur

```json
{
  "users": {
    "useridofmaliek": {
      "username": "Maliek Meersschaert",
      "password": "SOME HASH",
      "polls": {
        "1": {
          "name": "Amerikaanse verkiezingen",
          "options": {
            "Donald Trump": 10,
            "Hilary Clinton": 9,
            "Gary Johnson": 2,
            "Jill Stein": 1
          }
        }
    }
}
}
}
 ```
 
### Veldnamen
* users: veld met informatie van user
    * user_id: unieke id per user
    * username: naam van de user ==> string
    * password: paswoord van de user ==> hash
    * collection polls: alle polls die bij de user horen
        * id: unieke id van de poll    
        * name: naam van de poll ==> string    
        * collection options: de mogelijkheden van de poll
            * "Option": <value>: de keuze en bijhorende value