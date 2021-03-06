---
title: ODBC-Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- database classes [MFC], ODBC
- ODBC classes [MFC]
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
ms.openlocfilehash: a4cfa0d7afa197de7b65b6a0bd6b881a09534ef6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447697"
---
# <a name="odbc-classes"></a>ODBC-Klassen

Diese Klassenarbeiten mit den anderen Application Framework-Klassen zusammen, um einen einfachen Zugriff auf eine Vielzahl von Datenbanken zu erhalten, für die Open Database Connectivity (ODBC)-Treiber verfügbar sind.

Programme, die ODBC-Datenbanken verwenden, verfügen über mindestens ein `CDatabase` Objekt und ein `CRecordset`-Objekt.

[CDatabase](../mfc/reference/cdatabase-class.md)<br/>
Kapselt eine Verbindung mit einer Datenquelle, über die Sie die Datenquelle verwenden können.

[CRecordset](../mfc/reference/crecordset-class.md)<br/>
Kapselt eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt wurden. Recordsets ermöglichen das Scrollen von einem Datensatz zu einem Datensatz, das Aktualisieren von Datensätzen (hinzufügen, bearbeiten und Löschen von Datensätzen), das qualifizieren der Auswahl mit einem Filter, das Sortieren der Auswahl und das parametrialisieren der Auswahl mit Informationen, die zur Laufzeit abgerufen oder berechnet werden.

[CRecordView](../mfc/reference/crecordview-class.md)<br/>
Stellt eine Formularansicht bereit, die direkt mit einem Recordset-Objekt verbunden ist. Der DDX-Mechanismus (Dialog Datenaustausch) tauscht Daten zwischen dem Recordset und den Steuerelementen der Daten Satz Ansicht aus. Wie alle Formular Ansichten basiert eine Daten Satz Ansicht auf einer Dialogfeld Vorlagen-Ressource. Daten Satz Sichten unterstützen auch das Verschieben von Datensätzen in den Datensatz in das Recordset, Aktualisieren von Datensätzen und Schließen des zugeordneten Recordsets, wenn die Daten Satz Ansicht geschlossen wird.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Eine Ausnahme, die sich aus Fehlern bei der Datenzugriffs Verarbeitung ergibt. Diese Klasse erfüllt den gleichen Zweck wie andere Ausnahme Klassen im Mechanismus zur Ausnahmebehandlung der-Klassenbibliothek.

[CFieldExchange](../mfc/reference/cfieldexchange-class.md)<br/>
Liefert Kontextinformationen zur Unterstützung von Daten Satz Feld Austausch (RFX), der Daten zwischen den Felddatenmembern und Parameter Datenmembern eines Recordset-Objekts und den entsprechenden Tabellen Spalten in der Datenquelle austauscht. Analog zur Klasse [CDataExchange](../mfc/reference/cdataexchange-class.md), die auf ähnliche Weise für den Dialog Datenaustausch (Dialog Data Exchange, DDX) verwendet wird.

## <a name="related-classes"></a>Verwandte Klassen

[CLongBinary](../mfc/reference/clongbinary-class.md)<br/>
Kapselt ein Handle für den Speicher für einen Binary Large Object (BLOB), z. b. eine Bitmap. `CLongBinary` Objekte werden verwendet, um große Datenobjekte zu verwalten, die in Datenbanktabellen gespeichert werden.

[CDBVariant](../mfc/reference/cdbvariant-class.md)<br/>
Ermöglicht das Speichern eines Werts, ohne sich Gedanken über den Datentyp des Werts machen zu müssen. `CDBVariant` verfolgt den Datentyp des aktuellen Werts, der in einer Union gespeichert wird.

## <a name="see-also"></a>Weitere Informationen

[Klassen Übersicht](../mfc/class-library-overview.md)
