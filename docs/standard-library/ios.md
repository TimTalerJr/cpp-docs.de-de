---
title: '&lt;ios&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <ios>
- ios/std::<ios>
dev_langs: C++
helpviewer_keywords: ios header
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 04992f8324196c5fd762ba01a96fff7cc6ba6539
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltiosgt"></a>&lt;ios&gt;
Definiert verschiedene Typen und Funktionen, die grundlegend für den Umgang mit iostreams sind. Dieser Header wird in der Regel von einem anderen iostream-Header eingeschlossen. Sie müssen ihn nur selten direkt einschließen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <ios>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine große Gruppe von Funktionen sind Manipulatoren. Ein in \<ios> deklarierter Manipulator ändert die Werte, die im Argumentobjekt der Klasse [ios_base](../standard-library/ios-base-class.md) gespeichert sind. Andere Manipulatoren führen Aktionen für Streams aus, die von Objekten eines Typs gesteuert werden, der von dieser Klasse abgeleitet wurde, z.B. eine Spezialisierung einer der Vorlagenklassen [basic_istream](../standard-library/basic-istream-class.md) oder [basic_ostream](../standard-library/basic-ostream-class.md). [noskipws](../standard-library/ios-functions.md#noskipws)(**str**) beispielsweise löscht das Formatflag `ios_base::skipws` im Objekt **str**, das von einem dieser Typen sein kann.  
  
 Aufgrund von speziellen Einfüge- und Extraktionsvorgängen für die aus `ios_base` abgeleiteten Klassen können Sie einen Manipulator auch aufrufen, indem Sie ihn in einen Ausgabestream einfügen oder ihn aus einem Eingabestream extrahieren. Beispiel:  
  
```
istr>> noskipws;
```  
  
 Ruft [noskipws](../standard-library/ios-functions.md#noskipws)(**istr**) auf.  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[ios](../standard-library/ios-typedefs.md#ios)|Unterstützt die ios-Klasse aus der alten iostream-Bibliothek.|  
|[streamoff](../standard-library/ios-typedefs.md#streamoff)|Unterstützt interne Vorgänge.|  
|[streampos](../standard-library/ios-typedefs.md#streampos)|Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.|  
|[streamsize](../standard-library/ios-typedefs.md#streamsize)|Gibt die Größe des Streams an.|  
|[wios](../standard-library/ios-typedefs.md#wios)|Unterstützt die wios-Klasse aus der alten iostream-Bibliothek.|  
|[wstreampos](../standard-library/ios-typedefs.md#wstreampos)|Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.|  
  
### <a name="manipulators"></a>Manipulatoren  
  
|||  
|-|-|  
|[boolalpha](../standard-library/ios-functions.md#boolalpha)|Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als **TRUE** oder **FALSE** angezeigt werden.|  
|[dec](../standard-library/ios-functions.md#dec)|Gibt an, dass ganzzahlige Variablen in Basis-10-Schreibweise angezeigt werden.|  
|[defaultfloat](../standard-library/ios-functions.md#ios_defaultfloat)|Konfiguriert die Flags eines `ios_base`-Objekts, sodass ein Standard-Anzeigeformat für Floatwerte verwendet wird.|  
|[fixed](../standard-library/ios-functions.md#fixed)|Gibt an, dass eine Gleitkommazahl in fester Dezimalschreibweise angezeigt wird.|  
|[hex](../standard-library/ios-functions.md#hex)|Gibt an, dass ganzzahlige Variablen in Basis-16-Schreibweise angezeigt werden.|  
|[internal](../standard-library/ios-functions.md#internal)|Bewirkt, dass ein Nummernzeichen linksbündig und die Zahl rechtsbündig ausgerichtet wird.|  
|[left](../standard-library/ios-functions.md#left)|Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream linksbündig angezeigt wird.|  
|[noboolalpha](../standard-library/ios-functions.md#noboolalpha)|Gibt an, dass Variablen des Typs [bool](../cpp/bool-cpp.md) im Stream als 1 oder 0 angezeigt werden.|  
|[noshowbase](../standard-library/ios-functions.md#noshowbase)|Deaktiviert die Angabe der Schreibweisenbasis, mit der eine Zahl angezeigt wird.|  
|[noshowpoint](../standard-library/ios-functions.md#noshowpoint)|Zeigt nur den ganzzahligen Teil von Gleitkommazahlen an, dessen Bruchteil null ist.|  
|[noshowpos](../standard-library/ios-functions.md#noshowpos)|Bewirkt, dass positive Zahlen nicht explizit signiert werden.|  
|[noskipws](../standard-library/ios-functions.md#noskipws)|Bewirkt, dass Leerzeichen vom Eingabestream gelesen werden.|  
|[nounitbuf](../standard-library/ios-functions.md#nounitbuf)|Bewirkt, dass die Ausgabe gepuffert und verarbeitet wird, wenn der Puffer voll ist.|  
|[nouppercase](../standard-library/ios-functions.md#nouppercase)|Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Kleinbuchstaben angezeigt werden.|  
|[oct](../standard-library/ios-functions.md#oct)|Gibt an, dass ganzzahlige Variablen in Basis-8-Schreibweise angezeigt werden.|  
|[right](../standard-library/ios-functions.md#right)|Bewirkt, dass Text, der nicht so breit ist wie die Ausgabebreite, im Stream rechtsbündig angezeigt wird.|  
|[scientific](../standard-library/ios-functions.md#scientific)|Bewirkt, dass Gleitkommazahlen in wissenschaftlicher Schreibweise angezeigt werden.|  
|[showbase](../standard-library/ios-functions.md#showbase)|Gibt die Schreibweisenbasis an, mit der eine Zahl angezeigt wird.|  
|[showpoint](../standard-library/ios-functions.md#showpoint)|Zeigt den ganzzahligen Teil einer Gleitkommazahl und Ziffern rechts vom Dezimaltrennzeichen an, selbst wenn der Bruchteil null ist.|  
|[showpos](../standard-library/ios-functions.md#showpos)|Bewirkt, dass positive Zahlen explizit signiert werden.|  
|[skipws](../standard-library/ios-functions.md#skipws)|Bewirkt, dass Leerzeichen nicht vom Eingabestream gelesen werden.|  
|[unitbuf](../standard-library/ios-functions.md#unitbuf)|Bewirkt, dass die Ausgabe verarbeitet wird, wenn der Puffer nicht leer ist.|  
|[uppercase](../standard-library/ios-functions.md#uppercase)|Gibt an, dass hexadezimale Ziffern und der Exponent in wissenschaftlicher Schreibweise in Großbuchstaben angezeigt werden.|  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[basic_ios](../standard-library/basic-ios-class.md)|Die Vorlagenklasse beschreibt die Speicher- und Memberfunktionen, die Eingabestreams (der Vorlagenklasse [basic_istream](../standard-library/basic-istream-class.md)) und Ausgabestreams (der Vorlagenklasse[ basic_ostream](../standard-library/basic-ostream-class.md)) gemeinsam sind, die von den Vorlagenparametern abhängen.|  
|[fpos](../standard-library/fpos-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das alle Informationen, die zum Wiederherstellen eines beliebigen Dateipositionsindikators innerhalb eines Streams erforderlich sind, speichern kann.|  
|[ios_base](../standard-library/ios-base-class.md)|Die Klasse beschreibt die Speicher- und Memberfunktionen, die Eingabe- und Ausgabestreams gemeinsam sind, die nicht von den Vorlagenparametern abhängen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)


