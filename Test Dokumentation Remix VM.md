# **Test Dokumenation Remix VM**

In diesem Markdown-Dokument werden die Ergebnisse der Tests auf der lokalen Remix VM dokumentiert. Der Test auf der lokalen VM ist gemäss dem beschriebenen Testvorgehen der erste Schritt bei der Validierung des entwickelten Artefakts. Die Testfälle, welche durchlaufen werden, sind im Anhang der Arbeit dokumentiert, sowie im Testansatz im Kapitel 7.4 beschrieben.

### **Inhaltsverzeichnis zu den Testfällen**
1. [Testfall ID 0](#testfall0)
2. [Testfall ID 1](#testfall1)
3. [Testfall ID 2](#testfall2)
4. [Testfall ID 3](#testfall3)
5. [Testfall ID 4](#testfall4)
6. [Testfall ID 5](#testfall5)
7. [Testfall ID 6](#testfall6)
8. [Testfall ID 7](#testfall7)
9. [Testfall ID 8](#testfall8)
10. [Testfall ID 9](#testfall9)
11. [Testfall ID 10](#testfall10)

<div style="page-break-after: always;"></div>

## **Testfall ID 0 <a name="testfall0"></a>**

### **Testbeschreibung**
Der Testfall 0 ist nicht im Anhang der Arbeit beschrieben und stellt per se auch keinen Funktionstest dar. Der intelligente Vertrag soll in diesem Schritt kompiliert und auf der lokalen Remix VM lauffähig sein.

### **Input-Daten**
Alle intelligenten Verträge gemäss beschriebener technischer Implementierung in Kapitel 7.3:

1.	ImageShare.sol -> (Hauptvertrag)
	1.	IdentityManagement.sol
		1. AccessControl.sol
	2.	ERC721.sol
	3.	ERC721URIStorage.sol
	4.	ERC721Enumerable.sol
	5.	ERC721Burnable.sol

Die intelligenten Verträge sind im [GitHub](https://github.com/endrvc/Masterarbeit_Prototype) Repository verfügbar.

Ethereum-Konto mit welchem der Vertrag auf der lokalen Remix VM erstellt wird:	*0x5B38Da6a701c568545dCfcB03FcB875f56beddC4*

### **Erwartetes Ergebnis**

Alle Verträge kompilieren erfolgreich und der Hauptvertrag ImageShare.sol ist auf der lokalen Remix VM lauffähig. Ausserdem ist der Account, welcher den Vertrag aufsetzt, der Vertrags-Admin. Ausserdem werden mit dem aufsetzen des Vertrages auf der lokalen Blockchain die Rollen gemäss Lösungsdesign kreirt. Dabei ist der Vertrags-Admin der Rollen-Admin für die unabhängigen Prüfer. Diese sind wiederum der Rollen-Admin für Patienten, Ärzte sowie Kliniken.

### **Output-Daten**
Rückgabe-Status nach kompilieren und erstellen des Hauptvertrags:
```
Status:	true Transaction mined and execution succeed

Deployed Contract at Address:	0xd9145CCE52D386f254917e481eB44e9943F39138
```
### **Logs/Events**

```json
{
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x2f8788117e7eff1d82e926ec794901d17c78024a50270940304540a733656f0d",
		"event": "RoleGranted",
		"args": {
			"0": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"1": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"2": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"role": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"account": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"sender": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4"
		}
	},
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0xbd79b86ffe0ab8e8776151514217cd7cacd52c909f66475c3af44e129f0b00ff",
		"event": "RoleAdminChanged",
		"args": {
			"0": "0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed",
			"1": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"2": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09",
			"role": "0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed",
			"previousAdminRole": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"newAdminRole": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09"
		}
	},
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0xbd79b86ffe0ab8e8776151514217cd7cacd52c909f66475c3af44e129f0b00ff",
		"event": "RoleAdminChanged",
		"args": {
			"0": "0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a",
			"1": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"2": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09",
			"role": "0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a",
			"previousAdminRole": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"newAdminRole": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09"
		}
	},
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0xbd79b86ffe0ab8e8776151514217cd7cacd52c909f66475c3af44e129f0b00ff",
		"event": "RoleAdminChanged",
		"args": {
			"0": "0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5",
			"1": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"2": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09",
			"role": "0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5",
			"previousAdminRole": "0x0000000000000000000000000000000000000000000000000000000000000000",
			"newAdminRole": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09"
		}
	}
]
}
```


### **Resulat**

Der Hauptvertrag wurde erfolgreich kompiliert und auf der lokalen Remix VM Instanz erstellt. Aus den Logs ist ersichtlich, dass dem Ethereum-Konto, welches den Vertrag erstellt hat, die Admin-Rolle (0x00) zugewiesen wurde. Ausserdem wurden die restlichen Rollen erstellt und der Rollen-Admin für Patienten, Ärzte und Kliniken ist vom Admin (0x00) zur Rolle vom unabhängigen Prüfer (0x0ce23) gewechselt.

- [x] Bestanden
- [ ] Fehlgeschlagen


<div style="page-break-after: always;"></div>

## **Testfall ID 1 <a name="testfall1"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss dem Vertrags-Admin die Möglichkeit geben, unabhängige Prüfer auf der Blockchain zuzulassen, sowie deren digitale Identität abzubilden. Dabei dürfen nur unsensible Metadaten wie der Hashwert des Identitätsdokuments, der «Public Key» sowie die Ethereum-Adresse auf der Blockchain gespeichert werden. Die Zulassung und Abbildung ist dabei nur durch den Vertrags-Admin möglich.

### **Input-Daten**

Vertrags-Admin:	*0x5B38Da6a701c568545dCfcB03FcB875f56beddC4*

Ethereum-Konto des neuen unabhängigen Prüfers:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Drittes Ethereum-Konto, dass kein Vertrags-Admin ist:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

Die Metadaten des unabhängigen Prüfers, welche auf der Blockchain verankert werden sollen bei der Zulassung:
```json
{
	"bool _activ": true,
	"string _CID": "fe28a14fb95828a6afe93e1508068d3b0aa69eab8bece1c4938fa2967beca307",
	"string _public_key": "MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKBN+gIeBgKM84rXZUi3yI25d5nMmIe 9Q7bLlvWzor3V1GzLE9ggUo2OnmAX0Xcf4OExKTgT7Vc1dpmclD93RMCAwEAAQ==",
	"address _verifier_address": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
}
```

### **Erwartetes Ergebnis**

Es wird ein instanziertes `struct` erwartet mit den Metadaten des unabhängigen Prüfers, womit der unabhängige Prüfer auf der Blockchain zugelassen ist. Die Ethereum-Adresse, welche den Vertrag kompiliert und erstellt hat, ist in der Lage, andere Ethereum-Adressen als unabhängige Prüfer zu registrieren und zuzulassen. Die auf der Blockchain gespeicherten Metadaten sind nicht mehr als der Hashwert des Identitätsdokuments, der «Public Key» sowie die Ethereum-Adresse. Der Versuch einer anderen Ethereum-Adresse als jener des Vertrag-Admin, einen unabhängigen Prüfer zuzulassen, wird vom intelligenten Vertrag aufgrund der fehlenden Admin-Rolle zurückgewiesen.

### **Output-Daten**

Output-Daten beim Instanzierungsversuch mit einem dritten Ethereum-Konto (kein Vertrags-Admin):
```
transact to ImageShare.newVerifier errored: VM error: revert.

The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x4b20993bc481177ec7e8f571cecae8a9e22c02db is missing role 0x0000000000000000000000000000000000000000000000000000000000000000
```

Output-Daten beim Instanzierungsversuch mit dem Vertrags-Admin
```json
{
	"0": "uint256: id 0",
	"1": "bool: activ true",
	"2": "string: CID fe28a14fb95828a6afe93e1508068d3b0aa69eab8bece1c4938fa2967beca307",
	"3": "string: public_key MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKBN+gIeBgKM84rXZUi3yI25d5nMmIe/ 9Q7bLlvWzor3V1GzLE9ggUo2OnmAX0Xcf4OExKTgT7Vc1dpmclD93RMCAwEAAQ==",
	"4": "address: verifier_address 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
}
```

### **Logs/Events**

Emittierter Event nach dem erfolgreichen instanzieren durch den Vertrags-Admin, dass die Rolle des unabhängigen Prüfer gewährt wurde:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x2f8788117e7eff1d82e926ec794901d17c78024a50270940304540a733656f0d",
		"event": "RoleGranted",
		"args": {
			"0": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09",
			"1": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"2": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4",
			"role": "0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09",
			"account": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"sender": "0x5B38Da6a701c568545dCfcB03FcB875f56beddC4"
		}
	}
]
```
### **Resulat**
Das dritte Ethereum-Konto (0x4B2..) war nicht in der Lage, den unabhängigen Prüfer auf der Blockchain zuzulassen und wurde aufgrund der fehlenden Admin-Rolle zurückgewiesen. Der Vertrags-Admin (0x5B3..) konnte den unabhängigen Prüfer (0xAb8..) erfolgreich instanzieren und alle relevanten Metadaten sind auf der Blockchain verankert. Ausserdem wurde der Ethereum-Adresse des unabhägigen Prüfers erfolgreich die neue Rolle zugewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 2 <a name="testfall2"></a>

### Testbeschreibung

### Input-Daten

```

```

### Erwartetes Ergebnis

### Output-Daten

```

```

### Logs/Events


```

```

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 3 <a name="testfall3"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 4 <a name="testfall4"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 5 <a name="testfall5"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 6 <a name="testfall6"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 7 <a name="testfall7"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 8 <a name="testfall8"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 9 <a name="testfall9"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 10 <a name="testfall10"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen