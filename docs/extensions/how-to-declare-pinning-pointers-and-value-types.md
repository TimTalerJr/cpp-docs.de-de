---
title: 'Vorgehensweise: Deklarieren von festen Zeigern und Werttypen'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- value types, declaring
- pinning pointers
ms.assetid: 57c5ec8a-f85a-48c4-ba8b-a81268bcede0
ms.openlocfilehash: 901980c76aac5dd364f2fa2fae0e007f5d25f3d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65515735"
---
# <a name="how-to-declare-pinning-pointers-and-value-types"></a>Vorgehensweise: Deklarieren von festen Zeigern und Werttypen

Ein Werttyp kann implizit geschachtelt werden. Sie können dann einen festen Zeiger auf das Werttypobjekt selbst deklarieren und einen auf den geschachtelten Werttyp zeigenden **pin_ptr** verwenden.

## <a name="example"></a>Beispiel

### <a name="code"></a>Code

```cpp
// pin_ptr_value.cpp
// compile with: /clr
value struct V {
   int i;
};

int main() {
   V ^ v = gcnew V;   // imnplicit boxing
   v->i=8;
   System::Console::WriteLine(v->i);
   pin_ptr<V> mv = &*v;
   mv->i = 7;
   System::Console::WriteLine(v->i);
   System::Console::WriteLine(mv->i);
}
```

```Output
8
7
7
```

## <a name="see-also"></a>Siehe auch

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)