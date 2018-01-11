---
title: iterator-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xutility/std::iterator
dev_langs: C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 689ec4ab19b2e5079c31ab0a8677d25acf4e8899
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iterator-struct"></a>iterator-Struktur
Eine leere Basisstruktur wird verwendet, um sicherzustellen, dass eine benutzerdefinierte Iteratorklasse ordnungsgemäß mit **iterator_trait**s funktioniert.  
  
## <a name="syntax"></a>Syntax  
```    
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };  
```    
## <a name="remarks"></a>Hinweise  
 Die Vorlagenstruktur wird als Basistyp für alle Iteratoren verwendet. Definiert den Membertypen  
  
- `iterator_category` (ein Synonym für den Vorlagenparameter `Category`).  
  
- `value_type` ( ein Synonym für den Vorlagenparameter **Type**).  
  
- `difference_type` (ein Synonym für den Vorlagenparameter `Distance`).  
  
- `distance_type` (ein Synonym für den Vorlagenparameter `Distance`).  
  
- `pointer` (ein Synonym für den Vorlagenparameter `Pointer`).  
  
- `reference` (ein Synonym für den Vorlagenparameter `Reference`).  
  
 Beachten Sie, dass `value_type` kein konstanter Typ sein darf, auch wenn der **Zeiger** auf ein Objekt vom const-**Type** verweist und der Verweis ein Objekt vom const-**Type** kennzeichnet.  
  
## <a name="example"></a>Beispiel  
 Unter [iterator_traits](../standard-library/iterator-traits-struct.md) finden Sie ein Beispiel für das Deklarieren und Verwenden von Typen in der Iterator-Basisklasse.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Siehe auch  
 [\<iterator>](../standard-library/iterator.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)


