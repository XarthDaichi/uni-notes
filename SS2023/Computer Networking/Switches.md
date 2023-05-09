
Los switches tienen una tabla de accesos

La tabla de **MAC ADDRESS**


>[!VLAN]
> - Para conectar switch y PC se usa el copper through
> - Para conectar dos switches se usa el Copper Cross-Over

```
en
conf t
VLAN #
name Lorem
do wr

// Para todos los VLAN
int fx/x
switchport mode access //sw m ac
switchport access vlan x // sw ac vlan #
do wr

// PARA los puertos entre switches
int fx/x
switchport mode trunk
switchport trunk allowed vlan all
do wr
```

```
// en el router

en 
conf t
int fx/x.#
encapsulation dot1Q #
ip add <gateway> <mask>
no sh
do wr

// en el switch
en conf t
int fx/x // puerto de router
switchport mode trunk
switchport trunk allowed vlan all
```

Además se puede hacer una LAN diferente para hacer una VLAN nativa para configuración segura correcta

Para ver la tabla de MAC ADDRESS del switch se usa `show mac-address-table`
