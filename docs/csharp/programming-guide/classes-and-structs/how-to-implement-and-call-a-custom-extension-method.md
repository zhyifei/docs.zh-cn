---
title: 如何：实现和调用自定义扩展方法（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 62dbbbfb7a63c8fb73661fe7d66e73d0eca73107
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752104"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a><span data-ttu-id="82a20-102">如何：实现和调用自定义扩展方法（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="82a20-102">How to: Implement and Call a Custom Extension Method (C# Programming Guide)</span></span>
<span data-ttu-id="82a20-103">本主题将介绍如何为任意 .NET 类型实现自定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="82a20-103">This topic shows how to implement your own extension methods for any .NET type.</span></span> <span data-ttu-id="82a20-104">客户端代码可以通过以下方法使用扩展方法，添加包含这些扩展方法的 DLL 的引用，以及添加 [using](../../../csharp/language-reference/keywords/using-directive.md) 指令，该指令指定在其中定义扩展方法的命名空间。</span><span class="sxs-lookup"><span data-stu-id="82a20-104">Client code can use your extension methods by adding a reference to the DLL that contains them, and adding a [using](../../../csharp/language-reference/keywords/using-directive.md) directive that specifies the namespace in which the extension methods are defined.</span></span>  
  
## <a name="to-define-and-call-the-extension-method"></a><span data-ttu-id="82a20-105">定义和调用扩展方法</span><span class="sxs-lookup"><span data-stu-id="82a20-105">To define and call the extension method</span></span>  
  
1.  <span data-ttu-id="82a20-106">定义包含扩展方法的静态[类](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)。</span><span class="sxs-lookup"><span data-stu-id="82a20-106">Define a static [class](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md) to contain the extension method.</span></span>  
  
     <span data-ttu-id="82a20-107">此类必须对客户端代码可见。</span><span class="sxs-lookup"><span data-stu-id="82a20-107">The class must be visible to client code.</span></span> <span data-ttu-id="82a20-108">有关可访问性规则的详细信息，请参阅[访问修饰符](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="82a20-108">For more information about accessibility rules, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
2.  <span data-ttu-id="82a20-109">将扩展方法实现为静态方法，并且使其可见性至少与所在类的可见性相同。</span><span class="sxs-lookup"><span data-stu-id="82a20-109">Implement the extension method as a static method with at least the same visibility as the containing class.</span></span>  
  
3.  <span data-ttu-id="82a20-110">此方法的第一个参数指定方法所操作的类型；此参数前面必须加上 [this](../../../csharp/language-reference/keywords/this.md) 修饰符。</span><span class="sxs-lookup"><span data-stu-id="82a20-110">The first parameter of the method specifies the type that the method operates on; it must be preceded with the [this](../../../csharp/language-reference/keywords/this.md) modifier.</span></span>  
  
4.  <span data-ttu-id="82a20-111">在调用代码中，添加 `using` 指令，用于指定包含扩展方法类的[命名空间](../../../csharp/language-reference/keywords/namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="82a20-111">In the calling code, add a `using` directive to specify the [namespace](../../../csharp/language-reference/keywords/namespace.md) that contains the extension method class.</span></span>  
  
5.  <span data-ttu-id="82a20-112">和调用类型的实例方法那样调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="82a20-112">Call the methods as if they were instance methods on the type.</span></span>  
  
     <span data-ttu-id="82a20-113">请注意，第一个参数并不是由调用代码指定，因为它表示要在其上应用运算符的类型，并且编译器已经知道对象的类型。</span><span class="sxs-lookup"><span data-stu-id="82a20-113">Note that the first parameter is not specified by calling code because it represents the type on which the operator is being applied, and the compiler already knows the type of your object.</span></span> <span data-ttu-id="82a20-114">你只需通过 `n` 提供形参 2 的实参。</span><span class="sxs-lookup"><span data-stu-id="82a20-114">You only have to provide arguments for parameters 2 through `n`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82a20-115">示例</span><span class="sxs-lookup"><span data-stu-id="82a20-115">Example</span></span>  
 <span data-ttu-id="82a20-116">以下示例实现 `CustomExtensions.StringExtension` 类中名为 `WordCount` 的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="82a20-116">The following example implements an extension method named `WordCount` in the `CustomExtensions.StringExtension` class.</span></span> <span data-ttu-id="82a20-117">此方法对 <xref:System.String> 类进行操作，该类指定为第一个方法参数。</span><span class="sxs-lookup"><span data-stu-id="82a20-117">The method operates on the <xref:System.String> class, which is specified as the first method parameter.</span></span> <span data-ttu-id="82a20-118">将 `CustomExtensions` 命名空间导入应用程序命名空间，并在 `Main` 方法内部调用此方法。</span><span class="sxs-lookup"><span data-stu-id="82a20-118">The `CustomExtensions` namespace is imported into the application namespace, and the method is called inside the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="82a20-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="82a20-119">Compiling the Code</span></span>  
 <span data-ttu-id="82a20-120">若要运行此代码，请将其复制并粘贴到已在 Visual Studio 中创建的 Visual C# 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="82a20-120">To run this code, copy and paste it into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="82a20-121">默认情况下，此项目面向 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 版，并且具有对 System.Core.dll 的引用和一个用于 System.Linq 的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="82a20-121">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="82a20-122">如果项目中缺少其中一个或多个要求，则可以手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="82a20-122">If one or more of these requirements are missing from the project, you can add them manually.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="82a20-123">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="82a20-123">.NET Framework Security</span></span>  
 <span data-ttu-id="82a20-124">扩展方法不存在特定的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="82a20-124">Extension methods present no specific security vulnerabilities.</span></span> <span data-ttu-id="82a20-125">始终不会将扩展方法用于模拟类型的现有方法，因为为了支持类型本身定义的实例或静态方法，已解决所有名称冲突。</span><span class="sxs-lookup"><span data-stu-id="82a20-125">They can never be used to impersonate existing methods on a type, because all name collisions are resolved in favor of the instance or static method defined by the type itself.</span></span> <span data-ttu-id="82a20-126">扩展方法无法访问扩展类中的任何隐私数据。</span><span class="sxs-lookup"><span data-stu-id="82a20-126">Extension methods cannot access any private data in the extended class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82a20-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="82a20-127">See Also</span></span>  
 [<span data-ttu-id="82a20-128">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="82a20-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="82a20-129">扩展方法</span><span class="sxs-lookup"><span data-stu-id="82a20-129">Extension Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
 [<span data-ttu-id="82a20-130">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="82a20-130">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [<span data-ttu-id="82a20-131">静态类和静态类成员</span><span class="sxs-lookup"><span data-stu-id="82a20-131">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="82a20-132">protected</span><span class="sxs-lookup"><span data-stu-id="82a20-132">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="82a20-133">internal</span><span class="sxs-lookup"><span data-stu-id="82a20-133">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
 [<span data-ttu-id="82a20-134">public</span><span class="sxs-lookup"><span data-stu-id="82a20-134">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="82a20-135">this</span><span class="sxs-lookup"><span data-stu-id="82a20-135">this</span></span>](../../../csharp/language-reference/keywords/this.md)  
 [<span data-ttu-id="82a20-136">namespace</span><span class="sxs-lookup"><span data-stu-id="82a20-136">namespace</span></span>](../../../csharp/language-reference/keywords/namespace.md)
