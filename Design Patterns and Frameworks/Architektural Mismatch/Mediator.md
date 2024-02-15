(auch [[Observer]] with ChangeManager/Eventbus, aus **Extensibility Patterns -> Flat Extension**)
…ist ein verhaltensorientiertes Entwurfsmuster, mit dem Sie chaotische Abhängigkeiten zwischen Objekten reduzieren können. Das Muster schränkt die direkte Kommunikation zwischen den Objekten ein und zwingt sie, nur über ein Mediator-Objekt zusammenzuarbeiten.
Es ist ein $n$-Wege-Proxy zur Kommunikation, kombiniert mit einer [[Bridge]]
## Aufbau
![[Pasted image 20231129134230.png]]
- **Components** enthalten Business-Logik, jedes hat Referenz zu Mediator (mittels Mediator-Interface; kennt tatsächliche Mediator-Klasse nicht -> austauschbar!)
- **Mediator Interface** deklariert Methoden, mit denen (mit) Komponenten kommuniziert wird (meist einzelne `notify(sender)`). Komponenten können dieser Methode jeglichen Kontext als Argument übergeben (inkl. eigene Objekte), aber nur sodass keine Kopplung zwischen Sender- /Empfängerklasse entsteht.
- **Concrete Mediators**: Kapseln Relationen zwischen Komponenten, halten idR. Referenzen zu allen Komponenten und verwalten möglicherweise auch ihren Lifecycle.
- Komponenten dürfen sich **anderer Komponenten nicht bewusst** sein - passiert etwas wichtiges in/mit einem Component darf dieses *nur den Mediator benachrichtigen* - dieser kann den Sender identifizieren und entscheiden, welche anderen Components darüber in Kenntnis gesetzt werden. Aus Komponentensicht ist das ganze System eine Blackbox, der *Sender weiß nicht an wen seine Nachricht geht*, und der *Empfänger weiß nicht wer gesendet hat.*

> [!information]
> Der Mediator dient zur **anonymen Kommunikation** (Sender/Empfänger kennen sich nicht) in **dynamischen Kommunikationsnetzen** (Sender/Empfänger voneinander unabhängig)



## Beispiel
![[Pasted image 20231129135029.png]]
```kotlin
class AuthenticationDialog : Mediator() {
	var title: String
	val loginOrRegisterChkBx: Checkbox
	val loginUsername, loginPassword: Textbox
	val regUsername, regPassword, regEmail: Textbox
	val ok, cancel: Button
	val rememberMe: Checkbox

	init { rememberMe = Checkbox(this) … }

	override fun notify(sender: Component, event: String) {
		if(sender == loginOrRegisterChkBx && event == "check")
			if(loginOrRegisterChkBx.checked)
				title = "Log in"
			else
				title = "Register"
				
		if(sender == okBtn && event == "click")
			if(loginOrRegisterChkBx.checked)
				if(!userFound)
					...
	}
}

open class Component(dialog: Mediator) { //<-- Components kennen nur Mediator
	fun click() = dialog.notify(this, "click")
	fun keypress() = dialog.notify(this, "keypress")
}
```

## Anwendung
- wenn es schwierig ist manche Klassen zu verändern, da sie stark mit einigen anderen Klassen gekoppelt sind
- wenn eine Komponente in einem anderen Programm nicht wiederverwendet werden kann, da es zu stark von anderen Komponenten abhängt
- wenn man etliche Component-Subklassen erstellt nur um etwas grundlegendes Verhalten in verschiedenen Kontexten wiederzuverwenden

## Beziehungen
- [[Chain of Responsibility]], [[Command]], *Mediator* und [[Observer]] kümmern sich auf unterschiedliche Weise um die Kommunikation zwischen Komponenten
- *Mediator* und [[Facade]] versuchen die Zusammenarbeit zwischen eng gekoppelten Klassen zu organisieren
- [[Observer]] und *Mediator* sind sehr ähnlich
	- Mediator möchte gegenseitige Abhängigkeiten in einem System eliminieren
	- Observer möchte 1-Weg-Kommunikation zwischen Objekten ermöglichen, wobei manche Objekte anderen untergeordnet sind.

## Role-based Design
![[Design Patterns als Role Models#Mediator]]