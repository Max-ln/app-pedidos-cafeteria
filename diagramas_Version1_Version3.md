# Diagramas UML - App de Pedidos

Paso 1: Diagrama de Casos de Uso
```mermaid
flowchart LR
    %% Actores
    jonathan((jonathan))
    max((max))
    Personal((Personal de\nCafetería))

    %% Límite del Sistema
    subgraph App de Pedidos
        UC1([Consultar menú])
        UC2([Hacer pedido])
        UC3([Pagar])
        UC4([Preparar pedido])
        UC5([Notificar pedido listo])
    end

    %% Relaciones
    jonathan --- UC1
    jonathan --- UC2
    max --- UC1
    max --- UC2
    
    %% Relación Include
    UC2 -. "<< include >>" .-> UC3
    
    Personal --- UC4
    Personal --- UC5