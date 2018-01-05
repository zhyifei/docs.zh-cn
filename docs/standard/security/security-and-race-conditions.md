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
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 73664df9c072189f11d451da46bc3019c8593ec9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="a3d0e-102">安全和争用条件</span><span class="sxs-lookup"><span data-stu-id="a3d0e-102">Security and Race Conditions</span></span>
<span data-ttu-id="a3d0e-103">需要关注的另一个方面是争用条件被利用的安全漏洞的可能性。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="a3d0e-104">有几种方法可能是在其中。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="a3d0e-105">请按照下面的副主题概述了一些开发人员必须避免主要缺陷。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="a3d0e-106">Dispose 方法中的争用条件</span><span class="sxs-lookup"><span data-stu-id="a3d0e-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="a3d0e-107">如果类的**释放**方法 (有关详细信息，请参阅[垃圾回收](../../../docs/standard/garbage-collection/index.md)) 不是同步，则可能会在该清理代码**释放**可以运行多个一次，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a3d0e-108">因为这**释放**未同步的实现，则可能`Cleanup`由第一个线程，然后之前第二个线程调用`_myObj`设置为**null**。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="a3d0e-109">这是否是安全隐患依赖于会发生什么情况时`Cleanup`代码运行。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="a3d0e-110">未同步的主要问题**释放**实现涉及使用如文件的资源句柄。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="a3d0e-111">处置不当可能会导致错误的句柄使用，这通常会造成安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="a3d0e-112">构造函数中的争用条件</span><span class="sxs-lookup"><span data-stu-id="a3d0e-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="a3d0e-113">在某些应用程序，它可能是可能的其他线程，以访问类成员之前已完全运行其类构造函数。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="a3d0e-114">你应查看所有的类构造函数，以确保如果这应发生这种情况，或者如有必要同步线程没有安全问题。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="a3d0e-115">使用缓存的对象的争用条件</span><span class="sxs-lookup"><span data-stu-id="a3d0e-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="a3d0e-116">缓存安全信息或使用代码访问安全性的代码[断言](../../../docs/framework/misc/using-the-assert-method.md)操作还可能容易受到攻击争用条件如果类的其他部分不正确同步，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="a3d0e-117">如果没有其他的路径`DoOtherWork`并且可以从使用同一对象的另一个线程中调用，则不受信任的调用方可以绕过请求。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="a3d0e-118">如果你的代码缓存安全信息，请确保你针对此漏洞查看它。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="a3d0e-119">终结器中的争用条件</span><span class="sxs-lookup"><span data-stu-id="a3d0e-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="a3d0e-120">对象中引用它然后释放其终结器中的静态或非托管资源，还会出现争用条件。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="a3d0e-121">如果多个对象共享的资源的操作在类的终结器中，这些对象必须同步所有对该资源的访问。</span><span class="sxs-lookup"><span data-stu-id="a3d0e-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d0e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3d0e-122">See Also</span></span>  
 [<span data-ttu-id="a3d0e-123">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="a3d0e-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
