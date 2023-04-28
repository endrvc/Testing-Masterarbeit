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

### **Erwartetes Ergebnis**

Alle Verträge kompilieren erfolgreich und der Hauptvertrag ImageShare.sol ist auf der lokalen Remix VM lauffähig. 

### **Output-Daten**

### **Logs/Events**

### **Resulat**

- [x] Bestanden
- [ ] Fehlgeschlagen


<div style="page-break-after: always;"></div>

## Testfall ID 1 <a name="testfall1"></a>

### Testbeschreibung

Test Test

### Input-Daten

```json
{
    "bool _activ": true,
	"string _CID": "test",
	"string _public_key": "test234",
	"address _verifier_address": "0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
}
```

### Erwartetes Ergebnis

Es wird ein instanziertes `struct` erwartet mit den Input-Daten.

### Output-Daten

Transaktions-Hash: 0x51fb714bd4b4ffeb93acdf8d20cc0ce87f6476edd178b1162002c34388543889

```json
{
	"0": "uint256: id 0",
	"1": "bool: activ true",
	"2": "string: CID test",
	"3": "string: public_key test234",
	"4": "address: verifier_address 0xAb8483F64d9C6d1EcF9b849Ae677dD3315835cb2"
}
```

### Logs/Events
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
### Resulat

- [x] Bestanden
- [ ] Fehlgeschlagen

<div style="page-break-after: always;"></div>

## Testfall ID 2 <a name="testfall2"></a>

### Testbeschreibung

### Input-Daten

### Erwartetes Ergebnis

### Output-Daten

### Logs/Events

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