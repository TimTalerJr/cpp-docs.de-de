---
title: Festlegen von Eigenschaften im Anbieter
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB providers, properties
- properties [C++], OLE DB provider
ms.assetid: 26a8b493-7ec4-4686-96d0-9ad5d2bca5ac
ms.openlocfilehash: 2cbb334ab15912fdcf6980461016976d869f5a84
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404506"
---
# <a name="setting-properties-in-your-provider"></a>Festlegen von Eigenschaften im Anbieter

Finden Sie die Eigenschaftengruppe und die Eigenschafts-ID für die gewünschte Eigenschaft an. Weitere Informationen finden Sie unter [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734(v=vs.85)) in die **OLE DB-Programmierreferenz**.

Finden Sie in den Anbietercode, die vom Assistenten generiert wird die für die Eigenschaftengruppe eigenschaftenzuordnung ein. Der Name der Eigenschaftengruppe entspricht in der Regel der Name des Objekts. Befehls- und Rowsetobjekte-Eigenschaften finden Sie in den Befehl oder das Rowset; Dateneigenschaften Quell- und Initialisierung finden Sie in das neue Datenquellenobjekt.

Fügen Sie in der eigenschaftenzuordnung eine [PROPERTY_INFO_ENTRY_EX](../../data/oledb/property-info-entry-ex.md) Makro. PROPERTY_INFO_ENTRY_EX vier Parameter:

- Die Eigenschafts-ID für Ihre Eigenschaft entspricht. Entfernen Sie die ersten sieben Zeichen ("DBPROP_"), ausgehend vom Anfang des Namen der Eigenschaft. Wenn Sie hinzufügen möchten z. B. `DBPROP_MAXROWS`, übergeben Sie `MAXROWS` als erstes Element. Ist dies eine benutzerdefinierte Eigenschaft, übergeben Sie die vollständige GUID-Namen (z. B. `DBMYPROP_MYPROPERTY`).

- Der variant-Typ der Eigenschaft (in [OLE DB-Eigenschaften](/previous-versions/windows/desktop/ms722734(v=vs.85)) in die **OLE DB-Programmierreferenz**). Geben Sie die VT_ Typ (z. B. VT_BOOL oder VT_I2), der Datentyp entspricht.

- Flags, um anzugeben, ob die Eigenschaft lesbar und schreibbar ist und der Gruppe, zu der er gehört. Der folgende Code gibt beispielsweise an eine Lese-/Schreibeigenschaft, die der Rowset-Gruppe gehören:

    ```cpp
    DBPROPFLAGS_ROWSET | DBPROPFLAGS_READ | DBPROPFLAGS_WRITE
    ```

- Der Basiswert der Eigenschaft. Dies ist möglicherweise `VARIANT_FALSE` Geben Sie für einen booleschen Wert oder 0 (null) für einen ganzzahligen Typ, z. B. Die Eigenschaft weist diesen Wert an, es sei denn, er geändert wird.

    > [!NOTE]
    > Einige Eigenschaften sind verbunden oder mit anderen Eigenschaften, z. B. Lesezeichen oder Aktualisieren von verkettet. Wenn ein Consumer eine Eigenschaft auf "true" setzt, kann auch eine andere Eigenschaft festgelegt werden. Über die Methode unterstützt die OLE DB-Anbietervorlagen [CUtlProps:: OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md).

## <a name="properties-ignored-by-microsoft-ole-db-providers"></a>Eigenschaften von Microsoft OLE DB-Anbieter ignoriert

Der Microsoft OLE DB-Anbieter ignoriert die folgenden OLE DB-Eigenschaften:

- `DBPROP_MAXROWS` funktioniert nur für schreibgeschützte Anbieter (d. h. `DBPROP_IRowsetChange` und `DBPROP_IRowsetUpdate` sind **"false"**); andernfalls diese Eigenschaft wird nicht unterstützt.

- `DBPROP_MAXPENDINGROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.

- `DBPROP_MAXOPENROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.

- `DBPROP_CANHOLDROWS` wird ignoriert. der Anbieter gibt einen eigenen Grenzwert an.

## <a name="see-also"></a>Siehe auch

[Arbeiten mit OLE DB-Anbietervorlagen](../../data/oledb/working-with-ole-db-provider-templates.md)