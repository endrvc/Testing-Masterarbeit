# **Testdokumentation Remix VM**

In diesem Markdown-Dokument werden die Ergebnisse der Tests auf der lokalen Remix VM dokumentiert. Der Test auf der lokalen VM ist gemäss dem beschriebenen Testvorgehen der erste Schritt bei der Validierung des entwickelten Artefakts. Die Testfälle, welche durchlaufen werden, sind im Anhang der Arbeit dokumentiert, sowie im Testansatz im Kapitel 5.4 beschrieben.

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

Der Testfall 0 ist nicht im Anhang der Arbeit beschrieben und stellt auch keinen Funktionstest dar. Der intelligente Vertrag soll in diesem Schritt kompiliert und auf der lokalen Remix VM lauffähig sein.

### **Input-Daten**

Alle intelligenten Verträge gemäss beschriebener technischer Implementierung in Kapitel 5.3:

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

Alle Verträge kompilieren erfolgreich und der Hauptvertrag ImageShare.sol ist auf der lokalen Remix VM lauffähig. Ausserdem ist das Konto, welches den Vertrag aufsetzt, der Vertrags-Admin. Ausserdem werden mit dem Aufsetzen des Vertrages auf dem Ethereum Testnetzwerk die Rollen gemäss Lösungsdesign kreiert. Dabei ist der Vertrags-Admin der Rollen-Admin für die unabhängigen Prüfer. Diese sind wiederum der Rollen-Admin für Patienten, Ärzte sowie Kliniken.

### **Output-Daten**

Rückgabe-Status nach kompilieren und erstellen des Hauptvertrags:
```
Status:	true Transaction mined and execution succeed

Deployed Contract at Address:	0xd9145CCE52D386f254917e481eB44e9943F39138
```

Die 5 Rollen gemäss Lösungsdesign wurden kreiert.

Bytes32 der Admin Rolle:
```json
{
	"0": "bytes32: 0x0000000000000000000000000000000000000000000000000000000000000000"
}
```
Bytes32 der Rolle des unabhängigen Prüfers:
```json
{
	"0": "bytes32: 0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09"
}
```
Bytes32 der Rolle des Patienten:
```json
{
	"0": "bytes32: 0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed"
}
```
Bytes32 der Rolle des Arztes:
```json
{
	"0": "bytes32: 0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a"
}
```
Bytes32 der Rolle der Klinik:
```json
{
	"0": "bytes32: 0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5"
}
```

### **Logs/Events**

Emittierte Events für die Erstellung der neuen Rollen, sowie Zuweisung der Admin-Rolle an das Ethereum-Konto, welche den Vertrag initialisiert hat:

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


### **Resultat**

Der Hauptvertrag wurde erfolgreich kompiliert und auf der lokalen Remix VM Instanz erstellt. Aus den Logs ist ersichtlich, dass dem Ethereum-Konto, welches den Vertrag erstellt hat, die Admin-Rolle (0x00..) zugewiesen wurde. Ausserdem wurden die restlichen Rollen erstellt und der Rollen-Admin für Patienten, Ärzte und Kliniken ist vom Admin (0x00..) zur Rolle vom unabhängigen Prüfer (0x0ce..) gewechselt.

- [x] Bestanden
- [ ] Fehlgeschlagen


<div style="page-break-after: always;"></div>

## **Testfall ID 1 <a name="testfall1"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss dem Vertrags-Admin die Möglichkeit geben, unabhängige Prüfer auf der Blockchain zuzulassen, sowie deren digitale Identität abzubilden. Dabei dürfen nur unsensible Metadaten wie der Hashwert des Identitätsdokuments, der «Public Key» sowie die Ethereum-Adresse auf der Blockchain gespeichert werden. Die Zulassung und Abbildung ist dabei nur durch den Vertrags-Admin möglich.

### **Input-Daten**

Vertrags-Admin:	*0x5B38Da6a701c568545dCfcB03FcB875f56beddC4*

Ethereum-Konto des neuen unabhängigen Prüfers:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Drittes Ethereum-Konto, welches kein Vertrags-Admin ist:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

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

Es wird ein instanziiertes `struct` erwartet mit den Metadaten des unabhängigen Prüfers, womit der unabhängige Prüfer auf der Blockchain zugelassen ist. Die Ethereum-Adresse, welche den Vertrag kompiliert und erstellt hat, ist in der Lage, andere Ethereum-Adressen als unabhängige Prüfer zu registrieren und zuzulassen. Die auf der Blockchain gespeicherten Metadaten sind nicht mehr als der Hashwert des Identitätsdokuments, der «Public Key» sowie die Ethereum-Adresse. Der Versuch einer anderen Ethereum-Adresse als jener des Vertrag-Admin, einen unabhängigen Prüfer zuzulassen, wird vom intelligenten Vertrag aufgrund der fehlenden Admin-Rolle zurückgewiesen.

### **Output-Daten**

Output-Daten bei der Instanziierung mit einem dritten Ethereum-Konto (kein Vertrags-Admin):
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x4b20993bc481177ec7e8f571cecae8a9e22c02db is missing role 0x0000000000000000000000000000000000000000000000000000000000000000
```

Output-Daten bei der Instanziierung mit dem Vertrags-Admin:
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

Emittierter Event nach dem erfolgreichen Instanziieren durch den Vertrags-Admin, dass die Rolle des unabhängigen Prüfers gewährt wurde:
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
### **Resultat**
Das dritte Ethereum-Konto (0x4B2..) war nicht in der Lage, den unabhängigen Prüfer auf der Blockchain zuzulassen und wurde aufgrund der fehlenden Admin-Rolle zurückgewiesen. Der Vertrags-Admin (0x5B3..) konnte den unabhängigen Prüfer (0xAb8..) erfolgreich instanziieren und alle relevanten Metadaten sind auf der Blockchain verankert. Ausserdem wurde der Ethereum-Adresse des unabhängigen Prüfers erfolgreich die neue Rolle zugewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 2 <a name="testfall2"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss der Rolle «unabhängiger Prüfer» die Möglichkeit geben, Patienten auf der Blockchain zuzulassen, sowie deren digitale Identität abzubilden. Dabei dürfen nur unsensible Metadaten auf der Blockchain gespeichert werden. Die Zulassung ist dabei nur durch den unabhängigen Prüfer möglich.


### **Input-Daten**

Unabhängiger Prüfer:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Ethereum-Konto des neuen Patienten:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

Drittes Ethereum-Konto, welches kein unabhängiger Prüfer ist:	*0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB*

Die Metadaten des Patienten, welche auf der Blockchain verankert werden sollen bei der Zulassung:
``` json
{
	"bool _activ": true,
	"string _CID": "eb6bf42250d4da07032090a0a8b8107679ab92a1c8631ec54d0ff1e59575a011",
	"string _public_key": "MFswDQYJKoZIhvcNAQEBBQADSgAwRwJAf0guvJXUv+Y55qQ2/nkQb1yiloGB0DV2UdkHqNdsRhSDYL9vdx5NUE4/ffZV2+MEnsa2ZZ9LXDBiIycv7mkPaQIDAQAB",
	"address _identity_address": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"bytes32 _role": "0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed"
}
```

### **Erwartetes Ergebnis**

Die durch den Vertrags-Admin zugelassenen unabhängigen Prüfer sind in der Lage, andere Ethereum-Adressen als Patienten zu registrieren und zuzulassen. Die auf der Blockchain gespeicherten Metadaten sind dabei keine sensitiven persönlichen Daten:

* ID des Patienten
* ID des unabhängigen Prüfers welcher den Patienten zugelassen hat
* Ob der Patientenaccount aktiv ist
* Der Hashwert des Identitätsdokuments
* Public Key
* Ethereum-Adresse des Patienten
* Rolle «Patient»

Der Versuch einer anderen Ethereum-Adresse als jener mit der Rolle des unabhängigen Prüfers, einen Patienten zuzulassen, wird vom intelligenten Vertrag aufgrund der fehlenden «Verifier» Rolle zurückgewiesen.


### **Output-Daten**

Output-Daten bei der Instanziierung mit einem dritten Ethereum-Konto (kein unabhängiger Prüfer):
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x78731d3ca6b7e34ac0f824c42a7cc18a495cabab is missing role 0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09".
```

Output-Daten bei der Instanziierung mit dem unabhängigen Prüfer:
```json
{
	"0": "uint256: id 0",
	"1": "uint256: verified_by 0",
	"2": "bool: activ true",
	"3": "string: CID eb6bf42250d4da07032090a0a8b8107679ab92a1c8631ec54d0ff1e59575a011",
	"4": "string: public_key MFswDQYJKoZIhvcNAQEBBQADSgAwRwJAf0guvJXUv+Y55qQ2/nkQb1yiloGB0DV2 UdkHqNdsRhSDYL9vdx5NUE4/ffZV2+MEnsa2ZZ9LXDBiIycv7mkPaQIDAQAB",
	"5": "address: identity_address 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"6": "bytes32: role 0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed"
}
```

### **Logs/Events**

Emittierter Event nach dem erfolgreichen Instanziieren durch den unabhängigen Prüfer, dass die Rolle des Patienten gewährt wurde:
```json
{
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x2f8788117e7eff1d82e926ec794901d17c78024a50270940304540a733656f0d",
		"event": "RoleGranted",
		"args": {
			"0": "0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed",
			"1": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"2": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"role": "0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed",
			"account": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"sender": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
		}
	}
]
}
```

### **Resultat**

Das dritte Ethereum-Konto (0x787..) war nicht in der Lage, den Patienten auf der Blockchain zuzulassen und wurde aufgrund der fehlenden Rolle des unabhängigen Prüfers zurückgewiesen. Der unabhängige Prüfer (0xAb8..) konnte den Patienten (0x4B2..) erfolgreich instanziieren und alle relevanten Metadaten sind auf der Blockchain verankert, inklusive der automatischen Verweisung des korrekten unabhängigen Prüfers, welcher die Validierung durchgeführt hat. Ausserdem wurde der Ethereum-Adresse des Patienten erfolgreich die neue Rolle zugewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 3 <a name="testfall3"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss der Rolle «unabhängiger Prüfer» die Möglichkeit geben, Ärzte auf der Blockchain zuzulassen, sowie deren digitale Identität abzubilden. Dabei dürfen nur unsensible Metadaten auf der Blockchain gespeichert werden. Die Zulassung ist dabei nur durch den unabhängigen Prüfer möglich.


### **Input-Daten**

Unabhängiger Prüfer:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Ethereum-Konto des neuen Arztes:	*0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB*

Drittes Ethereum-Konto, dass kein unabhängiger Prüfer ist:	*0x617F2E2fD72FD9D5503197092aC168c91465E7f2*

Die Metadaten des Arztes, welche auf der Blockchain verankert werden sollen bei der Zulassung:
``` json
{
	"bool _activ": true,
	"string _CID": "8c82bc3f393015ff2b030aaa65f647b5a5fdeef67710b7c33ca4d2b0b9dce771",
	"string _public_key": "MFswDQYJKoZIhvcNAQEBBQADSgAwRwJAbpQuBhjeIiBaV3GfM3rS5ymrnXxFuYFdcjVyvXhWe29ArMDKSo8WVAPI7kC95jEJh/laj27+jhow0uNuSmCcJQIDAQAB",
	"address _identity_address": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
	"bytes32 _role": "0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a"
}
```

### **Erwartetes Ergebnis**

Die durch den Vertrags-Admin zugelassenen unabhängigen Prüfer sind in der Lage, andere Ethereum-Adressen als Ärzte zu registrieren und zuzulassen. Die auf der Blockchain gespeicherten Metadaten sind dabei keine sensitiven persönlichen Daten:

* ID des Arztes
* ID des unabhängigen Prüfers welcher den Arzt zugelassen hat
* Ob der Arztaccount aktiv ist
* Der Hashwert des Identitätsdokuments
* Public Key
* Ethereum-Adresse des Arztes
* Rolle «Physician»

Der Versuch einer anderen Ethereum-Adresse als jener mit der Rolle des unabhängigen Prüfers, einen Arzt zuzulassen, wird vom intelligenten Vertrag aufgrund der fehlenden «Verifier» Rolle zurückgewiesen.

### **Output-Daten**

Output-Daten bei der Instanziierung mit einem dritten Ethereum-Konto (kein unabhängiger Prüfer):
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x617f2e2fd72fd9d5503197092ac168c91465e7f2 is missing role 0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea0"
```

Output-Daten bei der Instanziierung mit dem unabhängigen Prüfer:
```json
{
	"0": "uint256: id 1",
	"1": "uint256: verified_by 0",
	"2": "bool: activ true",
	"3": "string: CID 8c82bc3f393015ff2b030aaa65f647b5a5fdeef67710b7c33ca4d2b0b9dce771",
	"4": "string: public_key MFswDQYJKoZIhvcNAQEBBQADSgAwRwJAbpQuBhjeIiBaV3GfM3rS5ymrnXxFuYFdcjVyvXhWe29ArMDKSo8WVAPI7kC95jEJh/laj27+jhow0uNuSmCcJQIDAQAB",
	"5": "address: identity_address 0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
	"6": "bytes32: role 0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a"
}
```

### **Logs/Events**

Emittierter Event nach dem erfolgreichen Instanziieren durch den unabhängigen Prüfer, dass die Rolle des Arztes gewährt wurde:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x2f8788117e7eff1d82e926ec794901d17c78024a50270940304540a733656f0d",
		"event": "RoleGranted",
		"args": {
			"0": "0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a",
			"1": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
			"2": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"role": "0xdc79ce1dcb26124af199f3da60ab26f473af9721c4a30e7db085946f824c3a3a",
			"account": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
			"sender": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
		}
	}
]
```

### **Resultat**

Das dritte Ethereum-Konto (0x617..) war nicht in der Lage, den Arzt auf der Blockchain zuzulassen und wurde aufgrund der fehlenden Rolle des unabhängigen Prüfers zurückgewiesen. Der unabhängige Prüfer (0xAb8..) konnte den Arzt (0x787..) erfolgreich instanziieren und alle relevanten Metadaten sind auf der Blockchain verankert, inklusive der automatischen Verweisung des korrekten unabhängigen Prüfers, welcher die Validierung durchgeführt hat. Ausserdem wurde der Ethereum-Adresse des Arztes erfolgreich die neue Rolle zugewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 4 <a name="testfall4"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss der Rolle «unabhängiger Prüfer» die Möglichkeit geben, Kliniken auf der Blockchain zuzulassen, sowie deren digitale Identität abzubilden. Dabei dürfen nur unsensible Metadaten auf der Blockchain gespeichert werden. Die Zulassung ist dabei nur durch den unabhängigen Prüfer möglich.

### **Input-Daten**

Unabhängiger Prüfer:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Ethereum-Konto der neuen Klinik:	*0x617F2E2fD72FD9D5503197092aC168c91465E7f2*

Drittes Ethereum-Konto, dass kein unabhängiger Prüfer ist:	*0x17F6AD8Ef982297579C203069C1DbfFE4348c372*

Die Metadaten der Klinik, welche auf der Blockchain verankert werden sollen bei der Zulassung:
``` json
{
	"bool _activ": true,
	"string _CID": "9e49fb2e0235162ee39d1ca9ad02c9dd9a6f3fca07d2fc1a1f7f196d6efdb518",
	"string _public_key": "MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKyJxi8QE8ZYnYxVVYhUtqNdhqmtPzXuUJmVNa4rh/I3fx30ldyS4zc74dg5rH8q6kOLMsQP5Y8xEepQh2hq36sCAwEAAQ==",
	"address _identity_address": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
	"bytes32 _role": "0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5"
}
```

### **Erwartetes Ergebnis**

Die durch den Vertrags-Admin zugelassenen unabhängigen Prüfer sind in der Lage, andere Ethereum-Adressen als Kliniken zu registrieren und zuzulassen. Die auf der Blockchain gespeicherten Metadaten sind dabei keine sensitiven persönlichen Daten:

* ID der Klinik
* ID des unabhängigen Prüfers welcher die Klinik zugelassen hat
* Ob der Klinikaccount aktiv ist
* Der Hashwert des Identitätsdokuments
* Public Key
* Ethereum-Adresse der Klinik
* Rolle «Hospital»

Der Versuch einer anderen Ethereum-Adresse als der mit der Rolle des unabhängigen Prüfers, eine Klinik zuzulassen, wird vom intelligenten Vertrag aufgrund der fehlenden Verifier-Rolle zurückgewiesen.

### **Output-Daten**

Output-Daten bei der Instanziierung mit einem dritten Ethereum-Konto (kein unabhängiger Prüfer):
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x17f6ad8ef982297579c203069c1dbffe4348c372 is missing role 0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1ea09"
```

Output-Daten bei der Instanziierung mit dem unabhängigen Prüfer:
```json
{
	"0": "uint256: id 2",
	"1": "uint256: verified_by 0",
	"2": "bool: activ true",
	"3": "string: CID 9e49fb2e0235162ee39d1ca9ad02c9dd9a6f3fca07d2fc1a1f7f196d6efdb518",
	"4": "string: public_key MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKyJxi8QE8ZYnYxVVYhUtqNdhqmtPzXuUJmVNa4rh/I3fx30ldyS4zc74dg5rH8q6kOLMsQP5Y8xEepQh2hq36sCAwEAAQ==",
	"5": "address: identity_address 0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
	"6": "bytes32: role 0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5"
}
```

### **Logs/Events**

Emittierter Event nach dem erfolgreichen Instanziieren durch den unabhängigen Prüfer, dass die Rolle der Klinik gewährt wurde:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x2f8788117e7eff1d82e926ec794901d17c78024a50270940304540a733656f0d",
		"event": "RoleGranted",
		"args": {
			"0": "0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5",
			"1": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
			"2": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2",
			"role": "0xc8f5b4140cca307cd927e59cbeea8291bffeee228fc677f0fa059aef7b4dd8d5",
			"account": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
			"sender": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
		}
	}
]
```

### **Resultat**

Das dritte Ethereum-Konto (0x17F..) war nicht in der Lage, die Klinik auf der Blockchain zuzulassen und wurde aufgrund der fehlenden Rolle des unabhängigen Prüfers zurückgewiesen. Der unabhängige Prüfer (0xAb8..) konnte die Klinik (0x617..) erfolgreich instanziieren und alle relevanten Metadaten sind auf der Blockchain verankert, inklusive der automatischen Verweisung des korrekten unabhängigen Prüfers, welcher die Validierung durchgeführt hat. Ausserdem wurde der Ethereum-Adresse der Klinik erfolgreich die neue Rolle zugewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 5 <a name="testfall5"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss Anpassung an den Metadaten der digitalen Identität ermöglichen, falls sich diese durch die Zeit ändern. Die Anpassung an den Metadaten soll nur durch das entsprechende Subjekt selbst möglich sein. Eine Ausnahme bildet der Hashwert des verifizierten Identitätsdokuments. Dies sollte nur durch den Admin bei einem unabhängigen Prüfer und durch den unabhängigen Prüfer bei einem Patienten, Arzt oder Klinik möglich sein.

### **Input-Daten**

Unabhängiger Prüfer:	*0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2*

Patient:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

Drittes Ethereum-Konto ohne Zulassung: *0x17F6AD8Ef982297579C203069C1DbfFE4348c372*

Folgende Metadaten des Patienten sollen angepasst werden:

Hashwert des Identitätsdokumentes (CID)
``` json
{
	"previousCID": "eb6bf42250d4da07032090a0a8b8107679ab92a1c8631ec54d0ff1e59575a011",
	"newCID": "62580fbe76142049a57602d3d4bbb9b2948f32a7ff48572ce1dc6c8b41100e3c"
}
```
Public Key
``` json
{
	"previousPublic_key": "MFswDQYJKoZIhvcNAQEBBQADSgAwRwJAf0guvJXUv+Y55qQ2/nkQb1yiloGB0DV2 UdkHqNdsRhSDYL9vdx5NUE4/ffZV2+MEnsa2ZZ9LXDBiIycv7mkPaQIDAQAB",
	"newPublic_key": "MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKIsiCaua6zIUQnK1KKdY6YFgVXOvXH+4baJ/M/ITmygbsFWfecoAoLFvO2V6jvi5wzE/FK4+zQ+I5md3uPKvn0CAwEAAQ=="
}
```
Aktivitätsstatus
``` json
{
	"previousActiv": true,
	"newActiv": false
}
```

### **Erwartetes Ergebnis**

Die einzelnen Identitäten können ihre **eigenen** Metadaten anpassen und keine anderen. Der Hashwert des verifizierten Identitätsdokuments kann nur durch eine höhere Hierarchiestufe angepasst werden, sprich Vertrags-Admin oder unabhängiger Prüfer.

### **Output-Daten**

**Anpassung des CID**

Anpassungsversuch durch den Patient selbst:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "AccessControl: account 0x4b20993bc481177ec7e8f571cecae8a9e22c02db is missing role 0x0ce23c3e399818cfee81a7ab0880f714e53d7672b08df0fa62f2843416e1e
```

Anpassungsversuch durch den unabhängigen Prüfer:
```json
{
	"address _identity_address": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"string _new_CID": "62580fbe76142049a57602d3d4bbb9b2948f32a7ff48572ce1dc6c8b41100e3c"
}
```

**Anpassung des Public Key**

Anpassungsversuch durch drittes Ethereum-Konto:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Unauthorized access".
```
Anpassungsversuch durch den Patienten selbst:
```json
{
	"address _identity_address": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"string _new_public_key": "MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKIsiCaua6zIUQnK1KKdY6YFgVXOvXH+4baJ/M/ITmygbsFWfecoAoLFvO2V6jvi5wzE/FK4+zQ+I5md3uPKvn0CAwEAAQ=="
}
```

**Anpassung des Aktivitätsstatus**

Anpassungsversuch durch drittes Ethereum-Konto:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Unauthorized access".
```
Anpassungsversuch durch den Patienten selbst:
```json
{
	"address _identity_address": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"bool _new_activ": false
}
```

**Übersicht aller Änderungen in den Stammdaten**
```json
{
	"0": "uint256: id 0",
	"1": "uint256: verified_by 0",
	"2": "bool: activ false",
	"3": "string: CID 62580fbe76142049a57602d3d4bbb9b2948f32a7ff48572ce1dc6c8b41100e3c",
	"4": "string: public_key MFwwDQYJKoZIhvcNAQEBBQADSwAwSAJBAKIsiCaua6zIUQnK1KKdY6YFgVXOvXH+4baJ/M/ITmygbsFWfecoAoLFvO2V6jvi5wzE/FK4+zQ+I5md3uPKvn0CAwEAAQ==",
	"5": "address: identity_address 0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"6": "bytes32: role 0x72606200fac42b7dc86b75901d61ecfab2a4a1a6eded478b97a428094891abed"
}
```

### **Logs/Events**

Keine Logs & Events bei diesem Testfall.

### **Resultat**

Der Patient (0x4B2..) selbst konnte seinen Public Key sowie seinen Aktivitätsstatus selbst ändern. Die Änderung des Hashwerts des Identitätsdokuments war dabei nur durch die nächst höhere Hierarchiestufe, den unabhängigen Prüfer (0xAb8..), möglich, nicht durch den Patienten selbst. Dritte Ethereum-Konten, konnten keine Änderungen an den Metadaten vornehmen und wurden vom intelligenten Vertrag aufgrund fehlender Autorisierung und Zulassung auf der Blockchain zurückgewiesen.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 6 <a name="testfall6"></a>**

### **Testbeschreibung**

Der intelligente Vertrag muss registrierten Ärzten und Kliniken die Möglichkeit geben, einen NFT-Token zu erstellen, welcher einen Befund darstellt. Der Inhaber des Tokens sollte dabei nur ein Patient sein können. Der URI-Link des NFT muss dabei ein IPFS CID sein können, damit keine Daten direkt auf der Blockchain gespeichert werden, jedoch die Datenintegrität, wie im Lösungsdesign beschrieben, sichergestellt werden kann.

### **Input-Daten**

**Metadaten auf IPFS**

Folgendes Metadaten JSON File wurde auf IFPS registriert:
```json
{
    "title": "Example Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "type": "string",
            "description": "http://localhost:8080",
            "hash": "2e414fb9d721f45a2797887de311b065cd4e93be8d06d9bad9ccf4efd0c4dcfc"
        }
    }
}
```
IPFS hat folgenden CID Hash als Zugangslink für das hochgeladene File generiert:

```
QmZ2ZmZisSGEZLqgVahHKAEavwTvZS7FXxXvVKwQjTkGag
```

**Ethereum-Konten**

Klinik:		*0x617F2E2fD72FD9D5503197092aC168c91465E7f2*

Patient:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

Drittes Ethereum-Konto:		*0x17F6AD8Ef982297579C203069C1DbfFE4348c372*

### **Erwartetes Ergebnis**

Ärzte und Kliniken sind in der Lage, einen neuen Token auf der Blockchain zu erstellen, welcher einen Befund darstellt. Der Versuch anderer Ethereum-Adresse als jener mit den Rollen «Physician» und «Hospital» wird vom intelligenten Vertrag aufgrund der fehlenden Rolle zurückgewiesen. Der Inhaber des Tokens kann dabei nur ein Patient sein, ansonsten wird der Token von der Blockchain nicht akzeptiert. Als URI-Link des Tokens wird ein IPFS-Link akzeptiert, womit die Datenintegrität gemäss Design, sichergestellt wird. Keine Befunddaten werden auf der Blockchain gespeichert.

### **Output-Daten**

Versuch der Registrierung eines Tokens durch einen Dritten für einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only Physician and Hospitals can mint new Token"
```

Versuch der Registrierung eines Tokens des Patienten für sich selbst:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only Physician and Hospitals can mint new Token"
```

Versuch der Registrierung eines Tokens durch die Klinik für einen Dritten ohne die Rolle "Patient":
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Mint only possible for patients"
```

Versuch der Registrierung eines Tokens durch die Klinik für sich selbst:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Mint only possible for patients"
```

Versuch der Registrierung eines Tokens durch die Klinik für einen Patienten:
```json
{
	"address to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
	"string uri": "QmZ2ZmZisSGEZLqgVahHKAEavwTvZS7FXxXvVKwQjTkGag"
}
```

### **Logs/Events**

Emittierter Event, dass ein neuer Token ausgegeben wurde:
```json
[
	{
		"from": "0xD7ACd2a9FD159E69Bb102A1ca21C9a3e3A5F771B",
		"topic": "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
		"event": "Transfer",
		"args": {
			"0": "0x0000000000000000000000000000000000000000",
			"1": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"2": "0",
			"from": "0x0000000000000000000000000000000000000000",
			"to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"tokenId": "0"
		}
	}
]

```

### **Resultat**

Die Ausgabe eines neuen Befundes (Tokens) ist nur durch eine Klinik oder Arzt für einen Patient möglich, alle anderen Szenarien werden vom intelligenten Vertrag zurückgewiesen. Ausserdem wird der IPFS CID Hash als URI-Link akzeptiert und auf der Blockchain erfolgreich registriert. Der intelligente Vertrag emittiert ebenfalls einen Event, dass ein neuer Token kreiert wurde, dies wird daran erkannt, dass die Herkunft-Adresse des Token 0x000 ist. 

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 7 <a name="testfall7"></a>**

### **Testbeschreibung**

Der intelligente Vertrag soll den Genehmigungsprozess abbilden können, welchen Kliniken und Ärzten der Patient Zugriff auf seine Daten gewährt. Dabei kann im intelligenten Vertrag die Genehmigung durch Ärzte und Kliniken angefragt werden, sowie der Patient die Anfragen genehmigen oder die Genehmigung widerrufen.

### **Input-Daten**

**Ethereum-Konten**

Konten welchen genutzt werden, um die verschiedenen Genehmigungen anzufragen:

Klinik:		*0x617F2E2fD72FD9D5503197092aC168c91465E7f2*

Arzt:		*0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB*

Patient:	*0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db*

Drittes Ethereum-Konto:		*0x17F6AD8Ef982297579C203069C1DbfFE4348c372*


### **Erwartetes Ergebnis**

Ärzte und Kliniken sind in der Lage, den Zugriff auf die Patientendaten anzufragen. Der Patient kann die Anfragen genehmigen, sowie Genehmigungen widerrufen. Die Anfrage nach einem Zugriff ist nur für die Rollen «Physician» und «Hospital» für eine Identität mit der Rolle «Patient» möglich. Die Genehmigung und Widerrufung sind nur für einen Patienten möglich.

### **Output-Daten**

**Anfrage der Genehmigung**

Versuch der Anfrage einer Genehmigung eines Dritten an einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can request approval."
```

Versuch der Anfrage einer Genehmigung eines Dritten an einen Arzt:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can request approval."
```

Versuch der Anfrage einer Genehmigung eines Arztes an einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Patient can be requested for approvals."
```

Versuch der Anfrage einer Genehmigung eines Arztes an einen Patienten:
```json
{
	"address _patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db"
}
```

Versuch der Anfrage einer Genehmigung einer Klinik an einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Patient can be requested for approvals."
```

Versuch der Anfrage einer Genehmigung einer Klinik an einen Patienten:
```json
{
	"address _patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db"
}
```

**Erteilung der Genehmigung**

Versuch der Erteilung der Genehmigung durch einen Dritten an einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can be subject to approval."
```

Versuch der Erteilung der Genehmigung durch einen Dritten an einen Arzt:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Patient can grant approvals."
```

Versuch der Erteilung der Genehmigung durch einen Arzt an einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can be subject to approval."
```

Versuch der Erteilung der Genehmigung durch einen Arzt an einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can be subject to approval."
```

Versuch der Erteilung der Genehmigung durch einen Patienten an einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital can be subject to approval."
```

Versuch der Erteilung der Genehmigung durch einen Patienten an einen Arzt:
```json
{
	"address _identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB"
}
```

Versuch der Erteilung der Genehmigung durch einen Patienten an eine Klinik:
```json
{
	"address _identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2"
}
```

**Widerrufung der Genehmigung**

Versuch der Widerrufung der Genehmigung durch einen Dritten für einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital have approvals to be revoked"
```

Versuch der Widerrufung der Genehmigung durch einen Dritten für einen Arzt:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Patient revoke approvals."
```

Versuch der Widerrufung der Genehmigung durch einen Arzt für einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital have approvals to be revoked"
```

Versuch der Widerrufung der Genehmigung durch einen Arzt für einen Patienten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital have approvals to be revoked"
```

Versuch der Widerrufung der Genehmigung durch einen Patienten für einen Dritten:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "Only identities with role Physician or Hospital have approvals to be revoked"
```

Versuch der Widerrufung der Genehmigung durch einen Patienten für einen Arzt:
```json
{
	"address _identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB"
}
```

Versuch der Widerrufung der Genehmigung durch einen Patienten für eine Klinik:
```json
{
	"address _identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2"
}
```

### **Logs/Events**

**Anfrage der Genehmigung**

Emittierter Event, bei der Anfrage einer Genehmigung durch einen Arzt an einen Patienten:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x8f491ef69bf5d5051c16fff776856d82887c8230d1125ef92ce9f2aaf05ed4e5",
		"event": "ApprovalRequested",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB"
		}
	}
]
```

Emittierter Event, bei der Anfrage einer Genehmigung durch eine Klinik an einen Patienten:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x8f491ef69bf5d5051c16fff776856d82887c8230d1125ef92ce9f2aaf05ed4e5",
		"event": "ApprovalRequested",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2"
		}
	}
]
```

**Erteilung der Genehmigung**

Emittierter Event, bei der Erteilung einer Genehmigung durch einen Patienten an einen Arzt:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x744a29cbc651d1297d6bffa0d1e6b58a94c6f9665708be83fa0c115d805af53a",
		"event": "ApprovalGranted",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB"
		}
	}
]
```

Emittierter Event, bei der Erteilung einer Genehmigung durch einen Patienten an eine Klinik:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x744a29cbc651d1297d6bffa0d1e6b58a94c6f9665708be83fa0c115d805af53a",
		"event": "ApprovalGranted",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2"
		}
	}
]
```

**Widerrufung der Genehmigung**

Emittierter Event, bei der Widerrufung einer Genehmigung durch einen Patienten an einen Arzt:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x97a94ee714dc2c5c1889f6fe8e8909a95e0307c4b272c7df374bf76582099f87",
		"event": "ApprovalRevoked",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB"
		}
	}
]
```

Emittierter Event, bei der Widerrufung einer Genehmigung durch einen Patienten an eine Klinik:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0x97a94ee714dc2c5c1889f6fe8e8909a95e0307c4b272c7df374bf76582099f87",
		"event": "ApprovalRevoked",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
			"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"_identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2"
		}
	}
]
```

### **Resultat**

Ärzte und Kliniken sind in der Lage, den Zugriff auf die Patientendaten anzufragen. Der Patient kann die Anfragen genehmigen, sowie Genehmigungen widerrufen. Die Anfrage nach einem Zugriff ist nur für die Rollen «Physician» und «Hospital» für eine Identität mit der Rolle «Patient» möglich. Die Genehmigung und Widerrufung sind nur für einen Patienten möglich.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 8 <a name="testfall8"></a>**

### **Testbeschreibung**

Der intelligente Vertrag soll die Genehmigungen in einer Tabelle erfassen, welche abgefragt werden kann, um den aktuellen Status der Genehmigung zwischen einem Patienten und einem Arzt/einer Klinik zu erfahren.

### **Input-Daten**

Folgende Genehmigungen wurden auf dem intelligenten Vertrag registriert:
```json
	"Genehmigung 1": {
		"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"_identityAddress": "0x78731D3Ca6b7E34aC0F824c42a7cC18A495cabaB",
		"bool": false
	}

	"Genehmigung 2": {
		"_patientAddress": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"_identityAddress": "0x617F2E2fD72FD9D5503197092aC168c91465E7f2",
		"bool": true
	}
```

### **Erwartetes Ergebnis**

Der aktuelle Status der Genehmigungen kann aus der Genehmigungs-Tabelle abgelesen werden.

### **Output-Daten**

Abfrage der Genehmigung zwischen dem Patienten (0x4B2..) und dem Arzt (0x787):
```json
{
	"0": "bool: false"
}
```

Abfrage der Genehmigung zwischen dem Patienten (0x4B2..) und der Klinik (0x617):
```json
{
	"0": "bool: true"
}
```

Abfrage einer Genehmigung, welche nicht im Genehmigungsprozess registriert wurde, zwischen zwei nicht auf der Blockchain registrierten Konten. Konto (0x17F) und Konto (0x5c6).
```json
{
	"0": "bool: false"
}
```

### **Logs/Events**

Keine Logs oder Events bei diesem Testfall.

### **Resultat**

Der aktuelle Status der registrierten Genehmigungen konnte korrekt von der Blockchain abgefragt werden. Für nicht registrierte Genehmigung wird der Standardwert "false" zurückgegeben.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 9 <a name="testfall9"></a>**

### **Testbeschreibung**

Innerhalb des intelligenten Vertrags kann nach allen Befunden (Tokens) eines spezifischen Patienten gefiltert werden und die Token URIs können abgefragt werden.

### **Input-Daten**

Es existieren zwei Tokens für den Patienten (0x4B2..):
```json
	"Token 1": {
		"address to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"string uri": "QmZ2ZmZisSGEZLqgVahHKAEavwTvZS7FXxXvVKwQjTkGag"
	}

	"Token 2": {
		"address to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"string uri": "QmabPUhqttoLfRueCjRroCMFUNCaGcmWmKWfffMkzx9dAE"
	}
```

### **Erwartetes Ergebnis**

Es kann nach allen Befunden (Tokens) zu einem Patienten gefiltert werden und die entsprechenden Token URI können abgefragt werden.

### **Output-Daten**

**Summe aller Token**

Zuerst wird mit der Funktion `balanceOf` angezeigt, wie viele Token die spezifische Adresse des Patienten (0x4B2..) besitzt:
```json
{
	"0": "uint256: 2"
}
```

**Filtern der relevanten Token-IDs**

Die Funktion `tokenOfOwnerByIndex` gibt die Token-ID zurück, die dem Patienten an einem gegebenen Index **seiner** Token-Liste gehört. Die Funktion `balanceOf` gibt die Länge des Index an, welcher mit `0` startet:

Index-Position 0
```json
{
	"0": "uint256: 0"
}
```

Index-Position 1
```json
{
	"0": "uint256: 1"
}
```

Index-Position 2
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "ERC721Enumerable: owner index out of bounds"
```

**Filtern nach der Token-URI**

Mit der Funktion `tokenURI` kann die Token-URI gegeben einer Token-ID abgerufen werden:

Token-ID 0
```json
{
	"0": "string: QmZ2ZmZisSGEZLqgVahHKAEavwTvZS7FXxXvVKwQjTkGag"
}
```

Token-ID 1
```json
{
	"0": "string: QmabPUhqttoLfRueCjRroCMFUNCaGcmWmKWfffMkzx9dAE"
}
```

**Abfrage der Metadaten mit Token-URI auf IPFS**

Rückgabe vom IPFS Gateway nach Eingabe des IPFS CID Hash (Token-URI):

Token-URI 0
```json
{
    "title": "Example Metadata",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "type": "string",
            "description": "http://localhost:8080",
            "hash": "2e414fb9d721f45a2797887de311b065cd4e93be8d06d9bad9ccf4efd0c4dcfc"
        }
    }
}
```

Token-URI 1
```json
{
    "title": "Example Metadata 2",
    "type": "object",
    "properties": {
        "name": {
            "type": "string",
            "description": "Identifies the asset to which this NFT represents"
        },
        "description": {
            "type": "string",
            "description": "Describes the asset to which this NFT represents"
        },
        "image": {
            "type": "string",
            "description": "http://localhost:8080",
            "hash": "9ef7420e2ed340a69a50ae128a3f5b27ace14b8526dc94d99a7e18bd9d7a21b0"
        }
    }
}
```

### **Logs/Events**

Keine Logs oder Events bei diesem Testfall.

### **Resultat**

Es war möglich nach den einzelnen Tokens des Patienten (0x4B2..) zu filtern und die entsprechenden Token-URIs abzurufen. In diesem Testing wurden die einzelnen Funktionen, welche dazu nötig sind, separat durchgeführt und dokumentiert. Es wäre jedoch möglich die Abfrage der einzelnen Funktionen durch Code zu automatisieren (z.B. JavaScript). Das IPFS-Gateway ausserhalb der Blockchain gibt ebenfalls, gegeben der Token-URIs, die korrekten Metadaten-Files zurück.

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## **Testfall ID 10 <a name="testfall10"></a>**

### **Testbeschreibung**

Der Patient soll in der Lage sein, seine eigenen Befunde (Tokens) zu löschen.

### **Input-Daten**

Es existieren zwei Tokens für den Patienten (0x4B2..):
```json
	"Token 1": {
		"address to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"string uri": "QmZ2ZmZisSGEZLqgVahHKAEavwTvZS7FXxXvVKwQjTkGag"
	}

	"Token 2": {
		"address to": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
		"string uri": "QmabPUhqttoLfRueCjRroCMFUNCaGcmWmKWfffMkzx9dAE"
	}
```
Der zweite Token sollte vernichtet werden.

### **Erwartetes Ergebnis**

Der Patient kann seine eigenen registrierten Befunde (Tokens) vernichten.

### **Output-Daten**

Der Versuch, den Token durch einen Arzt (0x787..) zu löschen:
```
The transaction has been reverted to the initial state.
Reason provided by the contract: "ERC721: caller is not token owner or approved"
```

Der Versuch, den Token durch den Patient selbst (0x4B2..) zu löschen:
```json
{
	"uint256 tokenId": "1"
}
```

### **Logs/Events**

Emittierter Event, dass der Token vernichtet wurde:
```json
[
	{
		"from": "0xd9145CCE52D386f254917e481eB44e9943F39138",
		"topic": "0xddf252ad1be2c89b69c2b068fc378daa952ba7f163c4a11628f55a4df523b3ef",
		"event": "Transfer",
		"args": {
			"0": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"1": "0x0000000000000000000000000000000000000000",
			"2": "1",
			"from": "0x4B20993Bc481177ec7E8f571ceCaE8A9e22C02db",
			"to": "0x0000000000000000000000000000000000000000",
			"tokenId": "1"
		}
	}
]
```

### **Resultat**

Der Token konnte erfolgreich nur durch den Patienten selbst vernichtet werden. Der intelligente Vertrag emittiert ebenfalls einen Event, dass ein Token vernichtet wurde, dies wird daran erkannt, dass die Transfer-Adresse des Token 0x000 ist.

- [x] Bestanden
- [ ] Fehlgeschlagen