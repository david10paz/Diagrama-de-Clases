***Empresa - Empleado - Cliente***
===


``` mermaid

classDiagram
    Proyecto o-- "1..*" Ciclo : {ordered}
    Ciclo o-- "4" Fase : {ordered}
    Ciclo -- Ejecutable
    Fase o-- "1..*" Iteración : {ordered}
    Iteración -- "1..*" Artefacto
    Artefacto <|-- Documento
    Artefacto <|-- Software
    Iteración o-- "1..*" Actividad
    Actividad "0..*" -- "0..*" Recurso
    Recurso <|-- Humano
    Recurso <|-- Material

    <!-- {ORDERED} da un significado de ordenación ante estructuras desoordenadas-->


    class Proyecto{
        -nombre : String
        - / avance : Float
    }
    class Ejecutable{
        -bytes
    }
    class Fase{
        -tipo : tipoFase
    }
    class Iteración{
        -comienzo : Date
    }
    class Actividad{
        -duracion : Integer
        -avance : Float
    }
    class Documento{
        -nombre : String
        -ubicacion
    }
    class Software{
        -bytes
    }
    class Humano{
        -nombre : String
    }
    class Material{
        inventario : String
    }

class tipoFase{
    <<enumeration>>
    inicio
    elaboracion
    construccion
    transicion
} 