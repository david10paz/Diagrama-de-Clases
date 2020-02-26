***Viajes***
===

``` mermaid

classDiagram
    Vuelo "0..*" -- "1" Avión : es realizado
    Vuelo "0..*" -- "0..* - PASAJERO" Persona : viaja
    Vuelo .. Billete
    Persona .. Billete



    class Vuelo{
        -plazas : Integer
        -fecha : Date
    }

    class Avión{
        -modelo : String
        -capacidad : Integer
    }

    class Persona{
        -nombre : String
        -apellidos: String
        -fechaNacimiento: Date
        -sexo : Género
    }

    class Billete{
        -asiento : Integer
    }

class Género{
    <<<enumeration>>
    hombre
    mujer
}