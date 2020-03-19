---
title: 安全和争用条件
'description:': Describes pitfalls to avoid around security holes exploited by race conditions, including dispose methods, constructors, cached objects, and finalizers.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
ms.openlocfilehash: 09d8d0d6e85af04fe0fb00f53df408126012081e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186784"
---
# <a name="security-and-race-conditions"></a>安全和争用条件
另一个令人关切的领域是，由于比赛条件，可能存在安全漏洞。 有几种方法可以做到这一点。 以下子主题概述了开发人员必须避免的一些主要缺陷。  
  
## <a name="race-conditions-in-the-dispose-method"></a>处置方法中的争用条件  
 如果类的**Dispose**方法（有关详细信息，请参阅[垃圾回收](../../../docs/standard/garbage-collection/index.md)）未同步，则 Dispose**内的清理**代码可能会运行多次，如以下示例所示。  
  
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
    if (myObj != null)
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 由于此**Dispose**实现不是同步的，因此第`Cleanup`一个线程可以调用第一个线程，然后将第`_myObj`二个线程设置为**null**。 这是否是一个安全问题，取决于`Cleanup`代码运行时会发生什么情况。 不同步的**Dispose**实现的主要问题是使用资源句柄（如文件）。 不当处置可能导致使用错误的句柄，这通常会导致安全漏洞。  
  
## <a name="race-conditions-in-constructors"></a>构造函数中的争用条件  
 在某些应用程序中，其他线程可能在其类构造函数完全运行之前访问类成员。 您应该查看所有类构造函数，以确保如果发生这种情况时没有安全问题，或者在必要时同步线程。  
  
## <a name="race-conditions-with-cached-objects"></a>具有缓存对象的争用条件  
 如果类的其他部分未适当同步，则缓存安全信息或使用代码访问安全[Assert](../../../docs/framework/misc/using-the-assert-method.md)操作的代码也可能容易受到争用条件的影响，如下例所示。  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False  
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
    if (SomeDemandPasses())
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false;  
    }  
}  
void DoOtherWork()
{  
    if (fCallersOK)
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
  
 如果可以从具有相同对象的另一`DoOtherWork`个线程调用其他路径，则不受信任的调用方可能会滑过请求。  
  
 如果代码缓存安全信息，请确保查看此漏洞。  
  
## <a name="race-conditions-in-finalizers"></a>终结器中的争用条件  
 争用条件也可能发生在引用静态或非托管资源的对象中，然后该资源在其终结器中释放。 如果多个对象共享在类的终结器中操作的资源，则对象必须同步对该资源的所有访问。  
  
## <a name="see-also"></a>另请参阅

- [代码安全维护指南](../../../docs/standard/security/secure-coding-guidelines.md)
