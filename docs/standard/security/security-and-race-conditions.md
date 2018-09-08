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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44210489"
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="f7b62-102">安全和争用条件</span><span class="sxs-lookup"><span data-stu-id="f7b62-102">Security and Race Conditions</span></span>
<span data-ttu-id="f7b62-103">需要关注的另一个方面是争用条件被利用的安全漏洞的可能性。</span><span class="sxs-lookup"><span data-stu-id="f7b62-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="f7b62-104">有几种方法可能是在其中。</span><span class="sxs-lookup"><span data-stu-id="f7b62-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="f7b62-105">遵循的子主题概述了一些开发人员必须避免的主要缺陷。</span><span class="sxs-lookup"><span data-stu-id="f7b62-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="f7b62-106">Dispose 方法中的争用条件</span><span class="sxs-lookup"><span data-stu-id="f7b62-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="f7b62-107">如果类的**释放**方法 (有关详细信息，请参阅[垃圾回收](../../../docs/standard/garbage-collection/index.md)) 不是同步，就可以清理代码内的**释放**可以运行多个一次，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f7b62-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="f7b62-108">因为这**Dispose**未同步实现，则很可能`Cleanup`调用的第一个线程，然后之前第二个线程`_myObj`设置为**null**。</span><span class="sxs-lookup"><span data-stu-id="f7b62-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="f7b62-109">这是否是安全问题上会发生什么情况取决于时`Cleanup`代码运行。</span><span class="sxs-lookup"><span data-stu-id="f7b62-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="f7b62-110">未同步的主要问题**Dispose**实现涉及的资源句柄，例如文件使用。</span><span class="sxs-lookup"><span data-stu-id="f7b62-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="f7b62-111">处置不当可能会导致错误的句柄使用，这通常会导致安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="f7b62-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="f7b62-112">在构造函数中的争用条件</span><span class="sxs-lookup"><span data-stu-id="f7b62-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="f7b62-113">在某些应用程序，可能会使其他线程来访问类成员之前已完全运行其类构造函数。</span><span class="sxs-lookup"><span data-stu-id="f7b62-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="f7b62-114">应检查所有的类构造函数，以确保如果这应是，或根据需要同步线程没有任何安全问题。</span><span class="sxs-lookup"><span data-stu-id="f7b62-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="f7b62-115">使用缓存的对象的争用条件</span><span class="sxs-lookup"><span data-stu-id="f7b62-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="f7b62-116">缓存安全信息或使用代码访问安全性的代码[Assert](../../../docs/framework/misc/using-the-assert-method.md)操作还可能易受攻击如果类的其他部分未正确同步，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="f7b62-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="f7b62-117">如果有其他路径`DoOtherWork`，可以使用同一个对象从其他线程调用时，不受信任调用方可以绕过请求。</span><span class="sxs-lookup"><span data-stu-id="f7b62-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="f7b62-118">如果您的代码缓存安全信息，请确保此漏洞查看它。</span><span class="sxs-lookup"><span data-stu-id="f7b62-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="f7b62-119">终结器中的争用条件</span><span class="sxs-lookup"><span data-stu-id="f7b62-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="f7b62-120">也可以引用静态或非托管资源，然后可以在其终结器释放的对象中出现争用条件。</span><span class="sxs-lookup"><span data-stu-id="f7b62-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="f7b62-121">如果多个对象共享的资源的类的终结器中操作，这些对象必须同步对该资源的所有访问。</span><span class="sxs-lookup"><span data-stu-id="f7b62-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b62-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7b62-122">See also</span></span>

- [<span data-ttu-id="f7b62-123">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="f7b62-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
