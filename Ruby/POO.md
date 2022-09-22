# Introduccion a POO en Ruby (Programacion orientada a objetos)

Esta es la forma en la que creamos una clase (Estas deben empezar en mayusculas usando CamelCase)

```ruby
class Person
end
```

Esta es la forma en la que creamos un objeto

```ruby
Person.new
```

## Metodos

para definir metodos en una clase lo hacemos de la siguiente forma

```ruby
class Person
    def greet
        "Hola"
    end
end
```

Para utilizar el metodo hacemos una instancia de la clase

```ruby
prueba = Person.new
puts prueba.greet
```

- El resultado del ejemplo anterior deberia ser "Hola"

## Hacer metodos privados

Para crear metodos que solo se ven dentro de una clase de hace de la siguiente forma

```ruby
Class Person
    ...
    private
    def metodo_secreto
        puts "Esto es un metodo privado"
    end
end
```

- Todos los metodos que escribamos luego de la palabra private son privados

## Metodo constructor

Las clases pueden tener un metodo `initialize` y este se llama automaticamente cada vez que creamos un objeto con `.new`

```ruby
Class Person
    def initialize
        puts "Creando una nueva persona"
    end
    ...
end
```

El metodo constructor tambien puede recibir argumentos

```ruby
Class person
    def initialize(nombre)
        puts "Creando una persona llamada #{nombre}"
    end
    ...
end
```

```ruby
Person.new("Sebastian")
```

- El resultado del ejemplo anterior deberia ser "Creando una persona llamada Sebastian"
