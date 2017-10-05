---
title: "Delegaten (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3175bf1c-86d8-4eda-8d8f-c5b6753d8e38
caps.latest.revision: 30
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 30
---
# Delegaten (C++/CX)
Das `delegate`\-Schlüsselwort wird verwendet, um einen Referenztyp zu deklarieren, der die [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Entsprechung eines Funktionsobjekts in Standard\-C\+\+ ist. Eine Delegatdeklaration ähnlich einer Funktionssignatur; sie gibt den Rückgabetyp und die Parametertypen an, über die die umschlossene Funktion verfügen muss. Dies ist eine benutzerdefinierte Delegatdeklaration:  
  
<!-- TODO: review snippet reference  [!CODE [cpp_winrtcomp#02](cpp_winrtcomp#02)]  -->  
  
 Delegaten werden am häufigsten in Verbindung mit Ereignissen verwendet. Ein Ereignis hat einen Delegattyp, ähnlich wie eine Klasse einen Schnittstellentyp haben kann. Der Delegat stellt einen Vertrag dar, den Ereignishandler erfüllen müssen. Im Folgenden wird ein Ereignisklassenmember dargestellt, der den Typ des zuvor definierten Delegaten hat:  
  
```  
event PrimeFoundHandler^ primeFoundEvent;  
```  
  
 Verwenden Sie beim Deklarieren von Delegaten, die Clients über die Anwendungsbinärdateischnittstelle der Windows Runtime bereitgestellt werden, [Windows::Foundation::TypedEventHandler\<TSender, TResult\>](http://msdn.microsoft.com/%20library/windows/apps/br225997.aspx). Dieser Delegat besitzt vordefinierte Proxy\- und Stubbinärdateien, die es ermöglichen, dass er von JavaScript\-Clients verwendet wird.  
  
## Verwenden von Delegaten  
 Wenn Sie eine [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)]\-App erstellen, arbeiten Sie häufig mit Delegaten als die Art von Ereignis, die eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Klasse verfügbar macht. Um ein Ereignis zu abonnieren, erstellen Sie eine Instanz des Delegattyps durch Angabe einer Funktion \(oder Lambda\), die mit der Delegatsignatur übereinstimmt. Verwenden Sie dann den `+=`\-Operator, um das Delegatobjekt an den Ereignismember in der Klasse zu übergeben. Dies wird als Abonnieren des Ereignisses bezeichnet. Wenn die Klasseninstanz das Ereignis auslöst, wird Ihre Funktion aufgerufen, zusammen mit allen anderen Handlern, die von Ihrem Objekt oder anderen Objekten hinzugefügt wurden.  
  
> [!TIP]
>  Visual Studio übernimmt viel Arbeit für Sie, wenn Sie einen Ereignishandler erstellen. Wenn Sie beispielsweise einen Ereignishandler in XAML\-Markup angeben, wird eine QuickInfo angezeigt. Wenn Sie die QuickInfo auswählen, erstellt Visual Studio automatisch die Ereignishandlermethode und ordnet sie dem Ereignis in der Veröffentlichungsklasse zu.  
  
 Das grundlegende Muster wird im folgenden Beispiel veranschaulicht.`Windows::Foundation::TypedEventHandler` ist der Delegattyp. Die Handlerfunktion wird erstellt, indem eine benannte Funktion verwendet wird.  
  
 In app.h:  
  
 [!code-cpp[cx_delegates#120](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#120)]  
  
 In app.cpp:  
  
 [!code-cpp[cx_delegates#121](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.cpp#121)]  
  
> [!WARNING]
>  Im Allgemeinen empfiehlt es sich bei einem Ereignishandler, eine benannte Funktion statt eines Lambda\-Ausdrucks zu verwenden. Andernfalls müssen Sie sorgfältig darauf achten, Zirkelverweise zu vermeiden. Eine benannte Funktion übernimmt den this\-Zeiger als schwachen Verweis, ein Lambda den this\-Zeiger allerdings als starken Verweis und erstellt einen Zirkelverweis. Weitere Informationen finden Sie unter [Schwache Verweise und unterbrochene Zyklen](../cppcx/weak-references-and-breaking-cycles-c-cx.md).  
  
 Gemäß der Konvention besitzen von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] definierte EventHandler\-Delegatnamen die Form \*EventHandler, zum Beispiel RoutedEventHandler, SizeChangedEventHandler oder SuspendingEventHandler. Außerdem haben Ereignishandlerdelegaten zwei Parameter und geben "ungültig" zurück. In einem Delegaten, der keine Typparameter aufweist, ist der erste Parameter vom Typ [Platform::Object Class^](../cppcx/platform-object-class.md); er enthält einen Verweis auf den Absender, also das Objekt, das das Ereignis ausgelöst hat. Sie müssen es wieder in den ursprünglichen Typ umwandeln, bevor Sie das Argument in der Ereignishandlermethode verwenden. In einem Eventhandlerdelegaten, der über Typparameter verfügt, gibt der erste Typparameter den Typ des Absenders an und der zweite Parameter ist ein Handle auf eine Verweisklasse, die Informationen zum Ereignis enthält. Der Name dieser Klasse lautet standardmäßig \*EventArgs. Beispielsweise verfügt ein RoutedEventHandler\-Delegat über einen zweiten Parameter des Typs RoutedEventArgs^ und DragEventHander verfügt über einen zweiten Parameter des Typs DragEventArgs^.  
  
 Gemäß der Konvention werden Delegaten, die den Code umschließen, der ausgeführt wird, wenn ein asynchroner Vorgang abgeschlossen ist, \*CompletedHandler benannt. Diese Delegaten werden als Eigenschaften in der Klasse, nicht als Ereignisse definiert. Verwenden Sie deshalb nicht den `+=`\-Operator, um sie zu abonnieren, sondern weisen der Eigenschaft nur ein Delegatobjekt zu.  
  
> [!TIP]
>  C\+\+ IntelliSense zeigt nicht die vollständige Signatur des Delegaten an; hilft Ihnen also nicht, den konkreten Typ des EventArgs\-Parameters zu bestimmen. Um den Typ zu finden, können Sie zum **Objektkatalog** wechseln und sich die `Invoke`\-Methode für den Delegaten ansehen.  
  
## Erstellen von benutzerdefinierten Delegaten  
 Sie können eigene Delegaten definieren, um Ereignishandler zu definieren oder Verbrauchern zu ermöglichen, benutzerdefinierte Funktionen an Ihre [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\- Komponente zu übergeben. Wie jeder andere [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ kann ein öffentlicher Delegat nicht als generisch deklariert werden.  
  
### Deklaration  
 Die Deklaration eines Delegaten ähnelt einer Funktionsdeklaration. Der Delegat ist hierbei jedoch ein Typ. In der Regel deklarieren Sie einen Delegaten im Namespace\-Gültigkeitsbereich, Sie können jedoch auch eine Delegatdeklaration innerhalb einer Klassendeklaration schachteln. Der folgende Delegat kapselt jede Funktion, die eine `ContactInfo^` als Eingabe akzeptiert und einen `Platform::String^` zurückgibt.  
  
 [!code-cpp[cx_delegates#111](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#111)]  
  
 Nachdem Sie einen Delegattyp deklariert haben, können Sie Klassenmember dieses Typs deklarieren, oder Methoden, die Objekte dieses Typs als Parameter akzeptieren. Eine Methode oder Funktion kann ebenfalls einen Delegattyp zurückgeben. Im folgenden Beispiel akzeptiert die `ToCustomString`\-Methode den Delegaten als Eingabeparameter. Die Methode ermöglicht Clientcode, eine benutzerdefinierte Funktion bereitzustellen, die eine Zeichenfolge aus einer der oder allen öffentlichen Eigenschaften eines `ContactInfo`\-Objekts erstellt.  
  
 [!code-cpp[Cx_delegates#112](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#112)]  
  
> [!NOTE]
>  Wenn Sie auf den Delegattyp verweisen, verwenden Sie – genau wie Sie bei einem beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Referenztyp – das "^"\-Symbol.  
  
 Eine Ereignisdeklaration verfügt immer über einen Delegattyp. Dieses Beispiel zeigt eine typische Delegattypsignatur in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] an:  
  
 [!code-cpp[cx_delegates#122](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#122)]  
  
 Das `Click`\-Ereignis in der `Windows:: UI::Xaml::Controls::Primitives::ButtonBase`\-Klasse ist vom Typ `RoutedEventHandler`. Weitere Informationen finden Sie unter [Ereignisse](../cppcx/events-c-cx.md).  
  
 Clientcode erstellt unter Verwendung von `ref new` zunächst die Delegatinstanz und stellt ein Lambda bereit, das mit der Signatur des Delegaten kompatibel ist und das benutzerdefinierte Verhalten definiert.  
  
 [!code-cpp[Cx_delegates#113](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.cpp#113)]  
  
 Anschließend wird die Memberfunktion aufgerufen und der Delegat übergeben. Angenommen, `ci` ist eine `ContactInfo^`\-Instanz und `textBlock` ein XAML\- `TextBlock^`.  
  
 [!code-cpp[Cx_delegates#114](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.cpp#114)]  
  
 Im nächsten Beispiel übergibt eine Client\-App einen benutzerdefinierten Delegaten an eine öffentliche Methode in einer [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente, die den Delegaten mit jedem Element in einem `Vector` ausführt:  
  
 [!code-cpp[Cx_delegates#118](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/clientapp/mainpage.xaml.cpp#118)]  
  
 [!code-cpp[Cx_delegates#119](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.cpp#119)]  
  
### Konstruktion  
 Sie können aus jedem der folgenden Objekte einen Delegaten erstellen:  
  
-   Lambda  
  
-   Statische Funktion  
  
-   Zeiger auf Member  
  
-   std::function  
  
 Im folgenden Beispiel wird gezeigt, wie aus jedem dieser Objekte ein Delegat erstellt wird. Sie verwenden den Delegaten auf genau die gleiche Weise, unabhängig vom zur Erstellung verwendeten Objekttyp.  
  
 [!code-cpp[Cx_delegates#115](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.cpp#115)]  
  
> [!WARNING]
>  Wenn Sie ein Lambda verwenden, das den this\-Zeiger aufzeichnet, stellen Sie sicher, dass Sie den `-=`\-Operator verwenden, um die Registrierung vor Beenden des Lambda explizit vom Ereignis aufzuheben. Weitere Informationen finden Sie unter [Ereignisse](../cppcx/events-c-cx.md).  
  
### Generische Delegate  
 Generische Delegaten in C\+\+\/CX haben die Einschränkungen, die den Deklarationen von generischen Klassen ähneln. Sie können nicht als öffentlich deklariert werden. Sie können einen privaten oder internen, generischen Delegaten deklarieren und ihn in C\+\+ nutzen, aber .NET oder JavaScript\-Clients können ihn nicht nutzen, da er nicht in die .winmd\-Metadaten ausgegeben wird. In diesem Beispiel wird ein generischer Delegat deklariert, der nur von C\+\+ genutzt werden kann:  
  
 [!code-cpp[Cx_delegates#116](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#116)]  
  
 Im folgenden Beispiel wird eine besondere Instanz des Delegaten innerhalb einer Klassendefinition deklariert:  
  
 [!code-cpp[Cx_delegates#117](../snippets/cpp/VS_Snippets_Misc/cx_delegates/cpp/delegatesevents/class1.h#117)]  
  
## Delegaten und Threads  
 Ein Delegat enthält, genau wie ein Funktionsobjekt, Code, der zu einem späteren Zeitpunkt ausgeführt wird. Wenn der Code, der den Delegaten erstellt und übergibt, und die Funktion, die den Delegaten akzeptiert und ausführt, im selben Thread ausgeführt werden, dann ist der Vorgang relativ einfach. Ist dieser Thread der UI\-Thread, kann der Delegat Benutzeroberflächenobjekte wie XAML\-Steuerelemente direkt bearbeiten.  
  
 Lädt eine Client\-App eine [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponente, die in einem Thread\-Apartment läuft, und stellt sie dieser Komponente einen Delegaten bereit, dann wird der Delegat standardmäßig direkt im STA\-Thread aufgerufen. Die meisten [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Komponenten können entweder in STA oder MTA ausgeführt werden.  
  
 Wenn der Code, der den Delegaten ausführt, in einem anderen Thread ausgeführt wird \(beispielsweise im Kontext eines concurrency::task\-Objekts\), dann sind Sie für das Synchronisieren des Zugriffs auf freigegebene Daten verantwortlich. Wenn der Delegat beispielsweise einen Verweis auf einen Vector enthält, und ein XAML\-Steuerelement verfügt über einen Verweis auf denselben Vector, müssen Sie Schritte unternehmen, um Deadlocks oder Racebedingungen zu vermeiden. Diese können auftreten, wenn sowohl der Delegat als auch das XAML\-Steuerelement versuchen, gleichzeitig auf den Vector zuzugreifen. Sie müssen außerdem darauf achten, dass der Delegat nicht versucht, durch Verweise lokale Variablen aufzuzeichnen, die vor Aufruf des Delegaten ungültig werden.  
  
 Wenn Sie möchten, dass der erstellte Delegat im gleichen Thread wieder aufgerufen wird, in dem er erstellt wurde – beispielsweise, wenn Sie ihn an eine Komponente übergeben, die in einem MTA Apartment ausgeführt wird – und Sie möchten, dass er im gleichen Thread wie der Ersteller aufgerufen wird, dann verwenden Sie die Delegatkonstruktorüberladung, die einen zweiten `CallbackContext`\-Parameter akzeptiert. Verwenden Sie diese Überladung nur bei Delegaten, die einen registrierten Proxy\/Stub haben; nicht alle in Windows.winmd definierten Delegaten sind registriert.  
  
 Wenn Sie mit Ereignishandlern in .NET vertraut sind, wissen Sie, dass die empfohlene Vorgehensweise darin besteht, eine lokale Kopie eines Ereignisses zu erstellen, bevor Sie es auslösen. Dies vermeidet Racebedingungen, in denen ein Ereignishandler möglicherweise entfernt würde, bevor das Ereignis aufgerufen wird. Es ist nicht erforderlich, dies in C\+\+\/CX zu bedenken, denn wenn Ereignishandler hinzugefügt oder entfernt werden, wird eine neue Handlerliste erstellt. Da ein C\+\+\-Objekt den Verweiszähler auf der Handlerliste erhöht, bevor ein Ereignis aufgerufen wird, ist sichergestellt, dass alle Handler gültig sind. Dies bedeutet auch, dass, wenn Sie einen Ereignishandler auf dem Consumerthread entfernen, dieser Handler möglicherweise weiterhin aufgerufen werden kann, wenn das Veröffentlichungsobjekt noch auf der Kopie der Liste funktioniert, die nun veraltet ist. Das Veröffentlichungsobjekt ruft die aktualisierte Liste erst bei der nächsten Auslösung des Ereignisses ab.  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)