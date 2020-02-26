Empresa - Empleado - Cliente
===

``` mermaid

classDiagram
    Persona <|-- Empleado
    Persona <|-- Cliente
    Empleado <|-- Directivo
    Empleado "0..*" -- "0..*" Directivo : subordinados
    Empresa "1..*" o-- "0..*" Cliente : clientes
    Empresa "1" *-- "1..*" Empleado : empleados


    class Persona{
        -nombre : String
        -edad : String
        +mostrar() void
    }

    class Empleado{
        -sueldo_bruto : String
        +mostrar() void
        +calcular_salario_neto() void
    }

    class Cliente{
        -telefono_de_contacto : INTEGER
        +mostrar() void
    }

    class Directivo{
        -categoria: String
        +mostrar() void
    }

    class Empresa{
        -nombre : String
    }