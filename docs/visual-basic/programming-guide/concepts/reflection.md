---
title: "反射 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: d991bc0f-d16a-4ac5-9351-70e5c5b9891b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: acfcb519128de0d616757398c94ec70dc7de6ef1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="reflection-visual-basic"></a><span data-ttu-id="9af1c-102">反射 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9af1c-102">Reflection (Visual Basic)</span></span>
<span data-ttu-id="9af1c-103">反射提供的对象 (类型的<xref:System.Type>)，用于描述程序集、 模块和类型。</xref:System.Type></span><span class="sxs-lookup"><span data-stu-id="9af1c-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules and types.</span></span> <span data-ttu-id="9af1c-104">可以使用反射动态地创建一种类型的实例，将类型绑定到现有对象，或从现有对象中获得的类型和调用它的方法或访问其字段和属性。</span><span class="sxs-lookup"><span data-stu-id="9af1c-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="9af1c-105">如果使用的在代码中的属性，可以利用反射来访问它们。</span><span class="sxs-lookup"><span data-stu-id="9af1c-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="9af1c-106">有关详细信息，请参阅[属性](https://msdn.microsoft.com/library/5x6cd29c)。</span><span class="sxs-lookup"><span data-stu-id="9af1c-106">For more information, see [Attributes](https://msdn.microsoft.com/library/5x6cd29c).</span></span>  
  
 <span data-ttu-id="9af1c-107">下面是一个简单的示例使用静态方法的反射的`GetType`-继承中的所有类型`Object`基类派生来获取变量的类型︰</span><span class="sxs-lookup"><span data-stu-id="9af1c-107">Here's a simple example of reflection using the static method `GetType` - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>  
  
```vb  
' Using GetType to obtain type information:  
Dim i As Integer = 42  
Dim type As System.Type = i.GetType()  
System.Console.WriteLine(type)  
```  
  
 <span data-ttu-id="9af1c-108">输出为︰</span><span class="sxs-lookup"><span data-stu-id="9af1c-108">The output is:</span></span>  
  
 `System.Int32`  
  
 <span data-ttu-id="9af1c-109">下面的示例使用反射来获取已加载程序集的完整名称。</span><span class="sxs-lookup"><span data-stu-id="9af1c-109">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>  
  
```vb  
' Using Reflection to get information from an Assembly:  
Dim info As System.Reflection.Assembly = GetType(System.Int32).Assembly  
System.Console.WriteLine(info)  
```  
  
 <span data-ttu-id="9af1c-110">输出为︰</span><span class="sxs-lookup"><span data-stu-id="9af1c-110">The output is:</span></span>  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
## <a name="reflection-overview"></a><span data-ttu-id="9af1c-111">反射概述</span><span class="sxs-lookup"><span data-stu-id="9af1c-111">Reflection Overview</span></span>  
 <span data-ttu-id="9af1c-112">反射是在以下情况下有用︰</span><span class="sxs-lookup"><span data-stu-id="9af1c-112">Reflection is useful in the following situations:</span></span>  
  
-   <span data-ttu-id="9af1c-113">当您需要访问程序的元数据中的特性。</span><span class="sxs-lookup"><span data-stu-id="9af1c-113">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="9af1c-114">有关详细信息，请参阅[检索信息存储在特性中](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)。</span><span class="sxs-lookup"><span data-stu-id="9af1c-114">For more information, see [Retrieving Information Stored in Attributes](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c).</span></span>  
  
-   <span data-ttu-id="9af1c-115">检查和实例化程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="9af1c-115">For examining and instantiating types in an assembly.</span></span>  
  
-   <span data-ttu-id="9af1c-116">构建在运行时的新类型。</span><span class="sxs-lookup"><span data-stu-id="9af1c-116">For building new types at runtime.</span></span> <span data-ttu-id="9af1c-117">使用中<xref:System.Reflection.Emit>。</xref:System.Reflection.Emit>类</span><span class="sxs-lookup"><span data-stu-id="9af1c-117">Use classes in <xref:System.Reflection.Emit>.</span></span>  
  
-   <span data-ttu-id="9af1c-118">用于执行后期绑定，访问在运行时创建的类型上的方法。</span><span class="sxs-lookup"><span data-stu-id="9af1c-118">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="9af1c-119">请参阅主题[动态加载和使用类型](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc)。</span><span class="sxs-lookup"><span data-stu-id="9af1c-119">See the topic [Dynamically Loading and Using Types](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9af1c-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="9af1c-120">Related Sections</span></span>  
 <span data-ttu-id="9af1c-121">更多相关信息：</span><span class="sxs-lookup"><span data-stu-id="9af1c-121">For more information:</span></span>  
  
-   [<span data-ttu-id="9af1c-122">反射</span><span class="sxs-lookup"><span data-stu-id="9af1c-122">Reflection</span></span>](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [<span data-ttu-id="9af1c-123">查看类型信息</span><span class="sxs-lookup"><span data-stu-id="9af1c-123">Viewing Type Information</span></span>](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [<span data-ttu-id="9af1c-124">反射和泛型类型</span><span class="sxs-lookup"><span data-stu-id="9af1c-124">Reflection and Generic Types</span></span>](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <span data-ttu-id="9af1c-125"><xref:System.Reflection.Emit></xref:System.Reflection.Emit></span><span class="sxs-lookup"><span data-stu-id="9af1c-125"><xref:System.Reflection.Emit></span></span>  
  
-   [<span data-ttu-id="9af1c-126">检索存储在特性中的信息</span><span class="sxs-lookup"><span data-stu-id="9af1c-126">Retrieving Information Stored in Attributes</span></span>](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a><span data-ttu-id="9af1c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9af1c-127">See Also</span></span>  
 <span data-ttu-id="9af1c-128">[Visual Basic 编程指南](../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9af1c-128">[Visual Basic Programming Guide](../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="9af1c-129"> [公共语言运行时中的程序集](https://msdn.microsoft.com/library/k3677y81)</span><span class="sxs-lookup"><span data-stu-id="9af1c-129"> [Assemblies in the Common Language Runtime](https://msdn.microsoft.com/library/k3677y81)</span></span>
