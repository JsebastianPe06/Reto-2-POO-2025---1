# Diagrama UML
Este diagrama simula una página de registro de notas de una intitución         
educativa cualquiera, relacionando los usuarios, las notas y grupos.

```mermaid
  classDiagram
    class Usuario{
        - nombre: string
        - ID: int
        - contraseña: string
        - correo: string
        - rol: string
        - fecha_de_creación
        - iniciar_Sesión()
        - actualizar_perfil()
        - ver_información()
    }
    class Estudiante{
        - grupo: int
        - notas: int
        - comentar()
        - reportar()
    }
    class Profesor{
        - materia: string
        - subir()
        - modificar_notas()
    }
    class Administrador{
        - permisos: string
        - lista_de_seguimiento: string
        - modificar_datos()
        - suspender()
        - notificar_cambios()
    }
    class Materia{
        - nombre: string
        - código: int
        - talleres: string
        - evaluaciones: string
    }
    class Grupo{
        - ID: int
        - estadísticas: int
    }
    Usuario <|-- Estudiante
    Usuario <|-- Profesor
    Usuario <|-- Administrador
    Grupo "1" o-- "40" Estudiante
    Profesor "1" o-- "2" Materia
    Grupo"1" *-- "*"Materia
