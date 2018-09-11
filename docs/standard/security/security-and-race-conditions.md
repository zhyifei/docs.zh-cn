---
title: 安全和争用条件
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ceaedc7c38ae70a0db5a7fd584a765a7474aff
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339329"
---
# <a name="security-and-race-conditions"></a>安全和争用条件
需要关注的另一个方面是争用条件被利用的安全漏洞的可能性。 有几种方法可能是在其中。 遵循的子主题概述了一些开发人员必须避免的主要缺陷。  
  
## <a name="race-conditions-in-the-dispose-method"></a>Dispose 方法中的争用条件  
 如果类的**释放**方法 (有关详细信息，请参阅[垃圾回收](../../../docs/standard/garbage-collection/index.md)) 不是同步，就可以清理代码内的**释放**可以运行多个一次，如下面的示例中所示。  
  
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
  
 因为这**Dispose**未同步实现，则很可能`Cleanup`调用的第一个线程，然后之前第二个线程`_myObj`设置为**null**。 这是否是安全问题上会发生什么情况取决于时`Cleanup`代码运行。 未同步的主要问题**Dispose**实现涉及的资源句柄，例如文件使用。 处置不当可能会导致错误的句柄使用，这通常会导致安全漏洞。  
  
## <a name="race-conditions-in-constructors"></a>在构造函数中的争用条件  
 在某些应用程序，可能会使其他线程来访问类成员之前已完全运行其类构造函数。 应检查所有的类构造函数，以确保如果这应是，或根据需要同步线程没有任何安全问题。  
  
## <a name="race-conditions-with-cached-objects"></a>使用缓存的对象的争用条件  
 缓存安全信息或使用代码访问安全性的代码[Assert](../../../docs/framework/misc/using-the-assert-method.md)操作还可能易受攻击如果类的其他部分未正确同步，如下面的示例中所示。  
  
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
  
 如果有其他路径`DoOtherWork`，可以使用同一个对象从其他线程调用时，不受信任调用方可以绕过请求。  
  
 如果您的代码缓存安全信息，请确保此漏洞查看它。  
  
## <a name="race-conditions-in-finalizers"></a>终结器中的争用条件  
 也可以引用静态或非托管资源，然后可以在其终结器释放的对象中出现争用条件。 如果多个对象共享的资源的类的终结器中操作，这些对象必须同步对该资源的所有访问。  
  
## <a name="see-also"></a>请参阅

- [安全编码准则](../../../docs/standard/security/secure-coding-guidelines.md)
