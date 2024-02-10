(Vererbung)

-> Strukturierung von Entitätstypen durch Zusammenfassen ähnlicher Typen
- Superklasse/Obertypen: alle gemeinsamen Eigenschaften
- Subklasse/Untertypen: Eigenschaften des Obertyps + weitere zusätzliche Attribute+Beziehungen

Jede Instanz der Subklasse ist immer auch Instanz der Superklasse, aber nicht umgekehrt!

![[Pasted image 20230502111824.png]]
(d=disjunkt)

## Umsetzung
![[Pasted image 20230502112926.png]]

### Universalrelation
- *Eine* Relation mit allen Attributen
- **Übliche Vorgehensweise**, Begrenzung in der Spaltenzahl
- 🙁 viele Spalten und viele NULL-Werte
![[Pasted image 20230502112549.png]]

### Horizontale Partitionierung
- Jede Entität wird eine separate Relation mit allen notwendigen Attributen
- Jedes Objekt genau ein Tupel in genau einer Relation (gleiche ID $\not =$ gleiches Objekt)
![[Pasted image 20230502112532.png]]

> [!example]- Umsetzung:
> ![[Pasted image 20230502113327.png]]
> 
> - Gemeinsame Extension mit allen gemeinsamen Attributen:
> ```sql
(SELECT "Product", id, price, stock FROM products)  
UNION  
(SELECT "Book", id, price, stock FROM book)  
UNION  
(SELECT "CD", id, price, stock FROM cd)
> ```
> - Rekonstruktion der Universalrelation:
> ```sql
(SELECT "Product",id,price,stock,NULL AS isbn,NULL AS title,NULL AS album, NULL AS artist FROM products)  
UNION  
(SELECT "Book",id,price,stock,isbn,title,NULL AS album,NULL AS artist FROM book)  
UNION  
(SELECT "CD",id,price,stock,NULL AS isbn,NULL AS title,album,artist FROM cd)
> ```
> --> **UNION** um Mengen zusammenfügen (gleiche Spaltenanzahl, Domäne nötig!)

### Vertikale Partitionierung
- Jede Entität wird eigene Relation mit Verknüpfung der Relationen
- Gesamtheit aller Attribute eines Objekts nur durch Verbund (*teuer!*)
- Referentielle Integrität (Fremdschlüssel) unterstützt direkt Vererbung
![[Pasted image 20230502112736.png]]

>[!example]- Umsetzung
> - Gemeinsame Extension mit allen gemeinsamen Attributen
> ```sql
SELECT id, price, stock  
FROM product
> ```
> - Rekonstruktion der Universalrelation
> ```sql
SELECT id, price, stock, isbn, title, album, artist  
FROM (product  
LEFT OUTER JOIN book ON product.id = book.id)  
LEFT OUTER JOIN cd ON product.id = cd.id
> ```
