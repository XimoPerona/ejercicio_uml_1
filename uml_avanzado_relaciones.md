classDiagram
    class Cliente {
        -String nombre
        -String email
        +realizarPedido()
        +obtenerPedidos()
    }

    class Pedido {
        -Date fecha
        -String estado
        +agregarLinea(LineaPedido linea)
        +calcularTotal()
    }

    class LineaPedido {
        -int cantidad
        +calcularSubtotal()
    }

    class Producto {
        -String nombre
        -double precio
        +getPrecio()
        +getNombre()
    }

    %% Relaciones
    Cliente "1" o-- "0..*" Pedido : realiza >
    Pedido "1" *-- "1..*" LineaPedido : compone >
    LineaPedido "1" o-- "1" Producto : refiere a >

}

Cliente "1" o-- "0..*" Pedido : realiza
Pedido "1" *-- "1..*" LineaPedido : contiene
LineaPedido "0..*" --> "1" Producto : producto

```
## Conclusión
- El prompt simplificado obtiene el mismo resultado detallado en el diagrama de clases.
- Es importante escribir las especificaciones lo más detalladas posible.
