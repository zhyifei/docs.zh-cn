---
title: "链接需求"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: faeeabeda89ea233e67b66b8848f5bbb665d3804
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="link-demands"></a><span data-ttu-id="363a8-102">链接需求</span><span class="sxs-lookup"><span data-stu-id="363a8-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="363a8-103">链接要求导致在实时编译过程中进行安全检查，并且只检查代码的直接调用程序集。</span><span class="sxs-lookup"><span data-stu-id="363a8-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="363a8-104">当代码绑定到类型引用（包括函数指针引用和方法调用）时发生链接。</span><span class="sxs-lookup"><span data-stu-id="363a8-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="363a8-105">如果调用程序集的权限不足以链接到代码，则加载并运行代码时将不允许该链接且将引发运行时异常。</span><span class="sxs-lookup"><span data-stu-id="363a8-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="363a8-106">可在继承自代码的类中重写链接要求。</span><span class="sxs-lookup"><span data-stu-id="363a8-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="363a8-107">请注意，不使用此类型的要求执行完整的堆栈审核，并且代码仍容易遭受引诱攻击。</span><span class="sxs-lookup"><span data-stu-id="363a8-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="363a8-108">例如，如果程序集 A 中的方法受链接要求，程序集 B 中的直接调用方被计算基于程序集 B 的权限 但是，此链接要求将不会计算程序集 C 中的方法如果间接调用该方法在程序集中使用的方法在程序集 b。此链接要求只指定直接权限中的直接调用程序集的调用方必须具有要链接到你的代码。</span><span class="sxs-lookup"><span data-stu-id="363a8-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="363a8-109">而不指定所有调用方为了运行你的代码所必须拥有的权限。</span><span class="sxs-lookup"><span data-stu-id="363a8-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="363a8-110"><xref:System.Security.CodeAccessPermission.Assert%2A>、<xref:System.Security.CodeAccessPermission.Deny%2A> 和 <xref:System.Security.CodeAccessPermission.PermitOnly%2A> 堆栈审核修饰符不影响链接要求计算。</span><span class="sxs-lookup"><span data-stu-id="363a8-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="363a8-111">由于链接要求不执行堆栈审核，所以堆栈审核修饰符对链接要求并无影响。</span><span class="sxs-lookup"><span data-stu-id="363a8-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="363a8-112">如果通过访问链接要求保护的方法[反射](../../../docs/framework/reflection-and-codedom/reflection.md)，则链接要求将检查通过反射访问的代码的直接调用方。</span><span class="sxs-lookup"><span data-stu-id="363a8-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="363a8-113">对于使用反射执行的方法发现和方法调用都是如此。</span><span class="sxs-lookup"><span data-stu-id="363a8-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="363a8-114">例如，假设代码使用反射来返回<xref:System.Reflection.MethodInfo>对象表示的方法受链接要求，然后再传递**MethodInfo**给使用该对象来调用原始方法的一些其他代码的对象。</span><span class="sxs-lookup"><span data-stu-id="363a8-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="363a8-115">在这种情况下，链接要求会检查两次： 一次针对返回的代码**MethodInfo**对象并一次性为对其进行调用的代码。</span><span class="sxs-lookup"><span data-stu-id="363a8-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="363a8-116">在静态类构造函数上执行的链接要求不保护构造函数，因为静态构造函数是在应用程序的代码执行路径外部由系统调用的。</span><span class="sxs-lookup"><span data-stu-id="363a8-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="363a8-117">因此，当链接要求应用于整个类时，它不能保护对静态构造函数的访问，尽管它确实保护类的其余部分。</span><span class="sxs-lookup"><span data-stu-id="363a8-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="363a8-118">下面的代码片段以声明方式指定链接到 `ReadData` 方法的任何代码必须具有 `CustomPermission` 权限。</span><span class="sxs-lookup"><span data-stu-id="363a8-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="363a8-119">此权限是假设的自定义权限，在 .NET Framework 中并不存在。</span><span class="sxs-lookup"><span data-stu-id="363a8-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="363a8-120">该请求由传递**SecurityAction.LinkDemand**标志切换为`CustomPermissionAttribute`。</span><span class="sxs-lookup"><span data-stu-id="363a8-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="363a8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="363a8-121">See Also</span></span>  
 [<span data-ttu-id="363a8-122">特性</span><span class="sxs-lookup"><span data-stu-id="363a8-122">Attributes</span></span>](../../../docs/standard/attributes/index.md)  
 [<span data-ttu-id="363a8-123">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="363a8-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
