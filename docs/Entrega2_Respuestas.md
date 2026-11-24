# Entrega 2: navegacion en el Web Framework

## From main -> Select-Zoom: que pasa con InvokingObject?
La vista se abre desde el menu, nadie la invoca: InvokingObject vale 0 y no hay contexto
previo (ni registro padre ni filtro). Select y Zoom funcionan de forma independiente.

## From child -> Zoom hijo - Select padre
Una vista de la tabla hija (jugador) abre la del padre (equipo). El Select del padre sirve
de busqueda y asigna la clave ajena (EquipoID) al hijo.

## From parent -> Zoom liga
La vista del padre (liga) abre la de sus hijos (equipo), filtrados por la liga actual.
1. Boton en Zoom liga que muestra los equipos de esa liga.
2. Sin boton: los equipos de la liga dentro del propio Zoom liga (lista hija del DD).

## Undefined -> Zoom jugador - Select posicion
No hay relacion directa: jugador no tiene PosicionID. La relacion es N:M mediante
jugadorposicion, asi que el Framework no puede filtrar ni asignar y la navegacion es undefined.
