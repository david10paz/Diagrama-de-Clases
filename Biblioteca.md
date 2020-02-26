Biblioteca
===

``` mermaid

classDiagram
    Copia "1...* EJEMPLAR" -- "LIBRO" Libro
    Copia "0..3" -- "0..1 LECTOR" Socio
    Copia .. Préstamo
    Socio .. Préstamo
    Libro "OBRA 1..*" -- "AUTOR" Autor
    Socio "SANCIONADO" -- "0..1 SANCION" Multa : recibe


    class Copia{
        -referencia : INTEGER
        -estado : EstadoCopia
    }

    class Libro{
        -titulo : String
        -editorial : String
        -año : INTEGER
        -tipo: Genero
    }

    class Autor{
        -nombre : String
        -nacionalidad : String
        -fechaNacimiento: Date
    }

    class Socio{
        -numero : INTEGER
        -nombre : String
        -direccion : String
        -telefono : INTEGER
    }

    class Préstamo{
        -inicio : Date
        -fin : Date
    }

    class Multa{
        -inicio : Date
        -fin : Date
    }

class Género{
    <<enumeration>>
    novela
    teatro
    poesia
    ensayo
}

class EstadoCopia{
    <<enumeration>>
    prestado
    retrasado
    biblioteca
    reparación
}
