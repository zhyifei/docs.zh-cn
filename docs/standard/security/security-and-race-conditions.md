---
title: "安全和争用条件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c092113f670c5799d98dcb13c9c713bbd1a47fb6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="security-and-race-conditions"></a>安全和争用条件
需要关注的另一个方面是争用条件被利用的安全漏洞的可能性。 有几种方法可能是在其中。 请按照下面的副主题概述了一些开发人员必须避免主要缺陷。  
  
## <a name="race-conditions-in-the-dispose-method"></a>Dispose 方法中的争用条件  
 如果类的**释放**方法 (有关详细信息，请参阅[垃圾回收](../../../docs/standard/garbage-collection/index.md)) 不是同步，则可能会在该清理代码**释放**可以运行多个一次，如下面的示例中所示。  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 因为这**释放**未同步的实现，则可能`Cleanup`由第一个线程，然后之前第二个线程调用`_myObj`设置为**null**。 这是否是安全隐患依赖于会发生什么情况时`Cleanup`代码运行。 未同步的主要问题**释放**实现涉及使用如文件的资源句柄。 处置不当可能会导致错误的句柄使用，这通常会造成安全漏洞。  
  
## <a name="race-conditions-in-constructors"></a>构造函数中的争用条件  
 在某些应用程序，它可能是可能的其他线程，以访问类成员之前已完全运行其类构造函数。 你应查看所有的类构造函数，以确保如果这应发生这种情况，或者如有必要同步线程没有安全问题。  
  
## <a name="race-conditions-with-cached-objects"></a>使用缓存的对象的争用条件  
 缓存安全信息或使用代码访问安全性的代码[断言](../../../docs/framework/misc/using-the-assert-method.md)操作还可能容易受到攻击争用条件如果类的其他部分不正确同步，如下面的示例中所示。  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 如果没有其他的路径`DoOtherWork`并且可以从使用同一对象的另一个线程中调用，则不受信任的调用方可以绕过请求。  
  
 如果你的代码缓存安全信息，请确保你针对此漏洞查看它。  
  
## <a name="race-conditions-in-finalizers"></a>终结器中的争用条件  
 对象中引用它然后释放其终结器中的静态或非托管资源，还会出现争用条件。 如果多个对象共享的资源的操作在类的终结器中，这些对象必须同步所有对该资源的访问。  
  
## <a name="see-also"></a>另请参阅  
 [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)
