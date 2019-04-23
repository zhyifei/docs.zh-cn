---
title: 访问自定义特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 764b0d535413fc1e5e23a2e47221789aa807ff38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321726"
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="5eb22-102">访问自定义特性</span><span class="sxs-lookup"><span data-stu-id="5eb22-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="5eb22-103">特性与程序元素相关联后，可使用反射来查询它们是否存在以及它们的值。</span><span class="sxs-lookup"><span data-stu-id="5eb22-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="5eb22-104">在 .NET Framework 1.0 和 1.1 版本中，在执行上下文中检查自定义特性。</span><span class="sxs-lookup"><span data-stu-id="5eb22-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="5eb22-105">.NET Framework 2.0 版本提供了新的加载上下文（仅反射上下文），可用于检查无法加载执行的代码。</span><span class="sxs-lookup"><span data-stu-id="5eb22-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="5eb22-106">仅反射上下文</span><span class="sxs-lookup"><span data-stu-id="5eb22-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="5eb22-107">加载到仅反射上下文中的代码无法执行。</span><span class="sxs-lookup"><span data-stu-id="5eb22-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="5eb22-108">这意味着不能创建自定义特性的实例，因为这将需要执行其构造函数。</span><span class="sxs-lookup"><span data-stu-id="5eb22-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="5eb22-109">若要在仅反射上下文中加载和检查自定义特性，请使用 <xref:System.Reflection.CustomAttributeData> 类。</span><span class="sxs-lookup"><span data-stu-id="5eb22-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="5eb22-110">可以通过使用静态 <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> 方法的相应重载来获取此类的实例。</span><span class="sxs-lookup"><span data-stu-id="5eb22-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5eb22-111">请参阅[如何：将程序集加载到仅反射上下文中](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)。</span><span class="sxs-lookup"><span data-stu-id="5eb22-111">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="5eb22-112">执行上下文</span><span class="sxs-lookup"><span data-stu-id="5eb22-112">The Execution Context</span></span>  
 <span data-ttu-id="5eb22-113">用于查询执行上下文中的特性的主要反射方法是 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> 和 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5eb22-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="5eb22-114">自定义特性的可访问性根据附加该特性的程序集来进行检查。</span><span class="sxs-lookup"><span data-stu-id="5eb22-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="5eb22-115">这相当于在附加自定义特性的程序集中检查一种类型的方法能否调用该自定义特性的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5eb22-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="5eb22-116"><xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> 等方法检查类型参数的可见性和可访问性。</span><span class="sxs-lookup"><span data-stu-id="5eb22-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="5eb22-117">只有包含用户定义类型的程序集中的代码才能使用 GetCustomAttributes 检索该类型的自定义特性。</span><span class="sxs-lookup"><span data-stu-id="5eb22-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="5eb22-118">以下 C# 示例是一种典型的自定义特性设计模式。</span><span class="sxs-lookup"><span data-stu-id="5eb22-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="5eb22-119">它说明运行时自定义特性反射模型。</span><span class="sxs-lookup"><span data-stu-id="5eb22-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```  
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="5eb22-120">如果运行时尝试为附加到 GetLanguage 方法的公共自定义特性类型 <xref:System.ComponentModel.DescriptionAttribute> 检索自定义特性，则它将执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5eb22-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1. <span data-ttu-id="5eb22-121">运行时检查 Type.GetCustomAttributes（类型 type） 的 DescriptionAttribute 类型参数是否是公共类型参数；如果是，则它可见且可访问。</span><span class="sxs-lookup"><span data-stu-id="5eb22-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2. <span data-ttu-id="5eb22-122">运行时检查从 DescriptionAttribute 派生的用户定义类型 MyDescriptionAttribute 在 System.Web.DLL 程序集（它在该程序集中附加到 GetLanguage() 方法）内是否可见和可以访问。</span><span class="sxs-lookup"><span data-stu-id="5eb22-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3. <span data-ttu-id="5eb22-123">运行时检查 MyDescriptionAttribute 的构造函数是否在 System.Web.DLL 程序集中可见和可以访问。</span><span class="sxs-lookup"><span data-stu-id="5eb22-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4. <span data-ttu-id="5eb22-124">运行时调用带有自定义特性参数的 MyDescriptionAttribute 的构造函数，然后将新对象返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="5eb22-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="5eb22-125">自定义特性反射模型可能会在定义类型的程序集外泄漏用户定义类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5eb22-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="5eb22-126">这与运行时系统库中返回用户定义类型的实例的成员（例如返回 RuntimeMethodInfo 对象数组的 <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>）相同。</span><span class="sxs-lookup"><span data-stu-id="5eb22-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="5eb22-127">为了防止客户端发现关于用户定义的自定义特性类型的信息，请将该类型的成员定义为非公共成员。</span><span class="sxs-lookup"><span data-stu-id="5eb22-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="5eb22-128">以下示例说明使用反射访问自定义特性的基本方法。</span><span class="sxs-lookup"><span data-stu-id="5eb22-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5eb22-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb22-129">See also</span></span>

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5eb22-130">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="5eb22-130">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="5eb22-131">反射的安全注意事项</span><span class="sxs-lookup"><span data-stu-id="5eb22-131">Security Considerations for Reflection</span></span>](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)
