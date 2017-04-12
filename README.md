# Code for the Talk at buildingIoT 2017

SourceCode and slides for the [talk "PRAXISBERICHT: EINE NATÜRLICHE BENUTZERSCHNITTSTELLE MIT AMAZON ECHO"](https://www.buildingiot.de/veranstaltung-5570-praxisbericht%3A-eine-nat%C3%BCrliche-benutzerschnittstelle-mit-amazon-echo.html?id=5570) at buildingIoT 2017.

[Download the slides](https://raw.githubusercontent.com/qaware/building-iot-2017/master/slides.pdf)

## Development

### Prerequisites

1. JDK 8

### Running

1. Run `mvnw spring-boot:run`

### Building

1. Run `mvnw clean package`
1. See `target` folder for fat jar

## Alexa skill configuration

### Intent schema

```json
{
  "intents": [
    {
      "intent": "QueryInventory",
      "slots": [
        {
          "name": "ware",
          "type": "LIST_OF_WARES"
        }
      ]
    },   
    {
      "intent": "OrderWare",
      "slots": [
        {
          "name": "ware",
          "type": "LIST_OF_WARES"
        }
      ]
    },
    {
      "intent": "LocateWare",
      "slots": [
        {
          "name": "ware",
          "type": "LIST_OF_WARES"
        }
      ]
    },
    {
      "intent": "AMAZON.CancelIntent"
    },
    {
      "intent": "AMAZON.StopIntent"
    }    
  ]
}
```

### Custom slot types

#### LIST_OF_WARES

```
Schrauben
Winkel
```


### Sample utterances

```
QueryInventory Wie viele {ware} haben wir noch
OrderWare Bestelle mir neue {ware}
LocateWare In welchem Regal befinden sich die {ware}
LocateWare Wo sind die {ware}
```

## License

[MIT License](LICENSE)

## Developer

Moritz Kammerer ([@phxql](https://github.com/phxql))
