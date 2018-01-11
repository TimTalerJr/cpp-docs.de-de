---
title: '&lt;memory&gt; enums | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 52ccd226214da7ddbdca9c480bb2f8940203155e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; enums
||  
|-|  
|[pointer_safety](#pointer_safety)|  
  
##  <a name="pointer_safety"></a> pointer_safety-Enumeration  
 Die Enumeration möglicher Werte, die von `get_pointer_safety` zurückgegeben werden.  
  
Klasse pointer_safety { relaxed, preferred, strict };  
  
### <a name="remarks"></a>Hinweise  
 Mit dem bereichsbezogenen `enum`-Element werden die Werte definiert, die von `get_pointer_safety()` zurückgegeben werden können:  
  
 `relaxed` – nicht sicher abgeleitete Zeiger (offensichtlich die Zeiger von deklarierten oder zugeordneten Objekte) werden genauso behandelt, wie die sicher abgeleiteten.  
  
 `preferred` – wie zuvor, aber nicht sicher abgeleitete Zeiger sollten nicht dereferenziert werden.  
  
 `strict` – nicht sicher abgeleitete Zeiger werden möglicherweise anders behandelt als sicher berechnete Zeiger.  
  
## <a name="see-also"></a>Siehe auch  
 [\<memory>](../standard-library/memory.md)


