---
title: "如何：将程序集加载到仅反射上下文中"
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
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebf25ec707ddb238431ffad35156b3a8cec7e4b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="0ef06-102">如何：将程序集加载到仅反射上下文中</span><span class="sxs-lookup"><span data-stu-id="0ef06-102">How to: Load Assemblies into the Reflection-Only Context</span></span>
<span data-ttu-id="0ef06-103">通过仅反射加载上下文，可检查为其他平台或 .NET Framework 的其他版本编译的程序集。</span><span class="sxs-lookup"><span data-stu-id="0ef06-103">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="0ef06-104">只能检查，不能执行加载到此上下文中的代码。</span><span class="sxs-lookup"><span data-stu-id="0ef06-104">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="0ef06-105">这意味着无法创建对象，因为无法执行构造函数。</span><span class="sxs-lookup"><span data-stu-id="0ef06-105">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="0ef06-106">因为该代码无法执行，所以不会自动加载依赖项。</span><span class="sxs-lookup"><span data-stu-id="0ef06-106">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="0ef06-107">如果需要对依赖项进行检查，必须自行加载。</span><span class="sxs-lookup"><span data-stu-id="0ef06-107">If you need to examine them, you must load them yourself.</span></span>  
  
### <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="0ef06-108">将程序集加载到仅反射加载上下文中</span><span class="sxs-lookup"><span data-stu-id="0ef06-108">To load an assembly into the reflection-only load context</span></span>  
  
1.  <span data-ttu-id="0ef06-109">使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> 方法重载可加载给定了显示名称的程序集，而使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> 方法可加载给定了路径的程序集。</span><span class="sxs-lookup"><span data-stu-id="0ef06-109">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="0ef06-110">如果该程序集为二进制文件映像，则使用 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> 方法重载。</span><span class="sxs-lookup"><span data-stu-id="0ef06-110">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ef06-111">不能使用仅反射上下文从非执行上下文中的 .NET Framework 版本加载 mscorlib.dll 版本。</span><span class="sxs-lookup"><span data-stu-id="0ef06-111">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>  
  
2.  <span data-ttu-id="0ef06-112">如果该程序集具有依赖项，<xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> 方法不会加载这些依赖项。</span><span class="sxs-lookup"><span data-stu-id="0ef06-112">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="0ef06-113">如果需要对依赖项进行检查，必须自行加载。</span><span class="sxs-lookup"><span data-stu-id="0ef06-113">If you need to examine them, you must load them yourself,.</span></span>  
  
3.  <span data-ttu-id="0ef06-114">使用程序集的 <xref:System.Reflection.Assembly.ReflectionOnly%2A> 属性确定是否已将程序集加载到仅反射上下文中。</span><span class="sxs-lookup"><span data-stu-id="0ef06-114">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>  
  
4.  <span data-ttu-id="0ef06-115">如果向程序集或程序集中的类型应用了特性，则应使用 <xref:System.Reflection.CustomAttributeData> 类检查这些特性，确保未尝试在仅反射上下文中执行代码。</span><span class="sxs-lookup"><span data-stu-id="0ef06-115">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="0ef06-116">使用 <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> 方法的适当重载获取表示应用于程序集、成员、模块或参数的特性的 <xref:System.Reflection.CustomAttributeData> 对象。</span><span class="sxs-lookup"><span data-stu-id="0ef06-116">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ef06-117">应用于程序集或其内容的特性可能是在该程序集中定义的，也可能是在加载到仅反射上下文中的另一个程序集中定义的。</span><span class="sxs-lookup"><span data-stu-id="0ef06-117">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="0ef06-118">无法事先知悉这些特性是在何处定义的。</span><span class="sxs-lookup"><span data-stu-id="0ef06-118">There is no way to tell in advance where the attributes are defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ef06-119">示例</span><span class="sxs-lookup"><span data-stu-id="0ef06-119">Example</span></span>  
 <span data-ttu-id="0ef06-120">以下代码示例演示如何检查应用于加载到仅反射上下文中的程序集的特性。</span><span class="sxs-lookup"><span data-stu-id="0ef06-120">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>  
  
 <span data-ttu-id="0ef06-121">本代码示例定义带有两个构造函数和一个属性的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="0ef06-121">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="0ef06-122">该特性可应用于程序集、在该程序集中声明的类型、该类型的方法以及该方法的参数。</span><span class="sxs-lookup"><span data-stu-id="0ef06-122">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="0ef06-123">执行时，该程序集将其本身加载到仅反射上下文中，并显示应用到程序集及其所含类型和成员的自定义特性的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0ef06-123">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ef06-124">为简化本代码示例，该程序集自行完成加载和检查操作。</span><span class="sxs-lookup"><span data-stu-id="0ef06-124">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="0ef06-125">通常情况下，不要在执行上下文和仅反射上下文中加载同一程序集。</span><span class="sxs-lookup"><span data-stu-id="0ef06-125">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>  
  
 [!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
 [!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
 [!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0ef06-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ef06-126">See Also</span></span>  
 <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>  
 <xref:System.Reflection.Assembly.ReflectionOnly%2A>  
 <xref:System.Reflection.CustomAttributeData>
