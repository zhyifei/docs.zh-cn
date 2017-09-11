---
title: "如何：将程序集加载到应用程序域中"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 75642ff3beb4462faa9068db76c89f3cb5f75ab8
ms.openlocfilehash: c319da0f8e6f3cdfb83e659a778136d668699834
ms.contentlocale: zh-cn
ms.lasthandoff: 08/10/2017

---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="31061-102">如何：将程序集加载到应用程序域中</span><span class="sxs-lookup"><span data-stu-id="31061-102">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="31061-103">可通过多种方法将程序集加载到应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="31061-103">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="31061-104">推荐方法是使用 <xref:System.Reflection.Assembly?displayProperty=fullName> 类的 `static`（在 Visual Basic 中为 `Shared`）<xref:System.Reflection.Assembly.Load%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="31061-104">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=fullName> class.</span></span> <span data-ttu-id="31061-105">加载程序集的其他方法包括：</span><span class="sxs-lookup"><span data-stu-id="31061-105">Other ways assemblies can be loaded include:</span></span>  
  
-   <span data-ttu-id="31061-106"><xref:System.Reflection.Assembly> 类的 <xref:System.Reflection.Assembly.LoadFrom%2A> 方法加载已给定其文件位置的程序集。</span><span class="sxs-lookup"><span data-stu-id="31061-106">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="31061-107">通过此方法加载程序集将使用不同的加载上下文。</span><span class="sxs-lookup"><span data-stu-id="31061-107">Loading assemblies with this method uses a different load context.</span></span>  
  
-   <span data-ttu-id="31061-108"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 和 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 方法将程序集加载到仅反射上下文中。</span><span class="sxs-lookup"><span data-stu-id="31061-108">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="31061-109">可检查但不可执行加载到该上下文中的程序集，允许检查以其他平台为目标的程序集。</span><span class="sxs-lookup"><span data-stu-id="31061-109">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="31061-110">请参阅[如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。</span><span class="sxs-lookup"><span data-stu-id="31061-110">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31061-111">仅反射上下文是 .NET Framework 2.0 版中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="31061-111">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
-   <span data-ttu-id="31061-112"><xref:System.AppDomain> 类的 <xref:System.AppDomain.CreateInstance%2A> 和 <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> 等方法可将程序集加载到应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="31061-112">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
-   <span data-ttu-id="31061-113"><xref:System.Type> 类的 <xref:System.Type.GetType%2A> 方法可加载程序集。</span><span class="sxs-lookup"><span data-stu-id="31061-113">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
-   <span data-ttu-id="31061-114"><xref:System.AppDomain?displayProperty=fullName> 类的 <xref:System.AppDomain.Load%2A> 方法可加载程序集，但主要用于实现 COM 互操作性。</span><span class="sxs-lookup"><span data-stu-id="31061-114">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=fullName> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="31061-115">不应使用该方法将程序集加载到除从其中调用该方法的应用程序域以外的其他应用程序域。</span><span class="sxs-lookup"><span data-stu-id="31061-115">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31061-116">从 .NET Framework 2.0 版开始，对于使用版本号高于当前已加载运行时的 .NET Framework 版本所编译的程序集，运行时将不再加载此类程序集。</span><span class="sxs-lookup"><span data-stu-id="31061-116">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="31061-117">这同样适用于主版本号和次版本号的组合。</span><span class="sxs-lookup"><span data-stu-id="31061-117">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="31061-118">可指定在应用程序域间共享已加载程序集的实时 (JIT) 编译代码的方式。</span><span class="sxs-lookup"><span data-stu-id="31061-118">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="31061-119">有关详细信息，请参阅[应用程序域和程序集](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)。</span><span class="sxs-lookup"><span data-stu-id="31061-119">For more information, see [Application Domains and Assemblies](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31061-120">示例</span><span class="sxs-lookup"><span data-stu-id="31061-120">Example</span></span>  
 <span data-ttu-id="31061-121">以下代码将名为“example.exe”或“example.dll”的程序集加载到当前应用程序域中，从该程序集获取名为 `Example` 的类型，为该类型获取名为 `MethodA` 的参数方法，然后执行该方法。</span><span class="sxs-lookup"><span data-stu-id="31061-121">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="31061-122">有关从已加载程序集中获取信息的完整讨论，请参阅[动态加载和使用类型](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md)。</span><span class="sxs-lookup"><span data-stu-id="31061-122">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../../../docs/framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 <span data-ttu-id="31061-123">[!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)] [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)] [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="31061-123">[!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)] [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)] [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31061-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31061-124">See Also</span></span>  
 <span data-ttu-id="31061-125"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A></span><span class="sxs-lookup"><span data-stu-id="31061-125"><xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A></span></span>   
 <span data-ttu-id="31061-126">[对应用程序域进行编程](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span><span class="sxs-lookup"><span data-stu-id="31061-126">[Programming with Application Domains](http://msdn.microsoft.com/en-us/bd36055b-56bd-43eb-b4d8-820c37172131) </span></span>  
 <span data-ttu-id="31061-127">[反射](../../../docs/framework/reflection-and-codedom/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="31061-127">[Reflection](../../../docs/framework/reflection-and-codedom/reflection.md) </span></span>  
 <span data-ttu-id="31061-128">[使用应用程序域](../../../docs/framework/app-domains/use.md) </span><span class="sxs-lookup"><span data-stu-id="31061-128">[Using Application Domains](../../../docs/framework/app-domains/use.md) </span></span>  
 <span data-ttu-id="31061-129">[如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) </span><span class="sxs-lookup"><span data-stu-id="31061-129">[How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) </span></span>  
 [<span data-ttu-id="31061-130">应用程序域和程序集</span><span class="sxs-lookup"><span data-stu-id="31061-130">Application Domains and Assemblies</span></span>](http://msdn.microsoft.com/en-us/433b04ae-4ba8-4849-9dbd-79194f240346)

