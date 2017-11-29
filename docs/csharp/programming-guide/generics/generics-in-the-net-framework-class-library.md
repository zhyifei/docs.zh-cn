---
title: ".NET Framework 类库中的泛型（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: generics [C#], in .NET Framework class library
ms.assetid: afdd5477-6770-4686-8297-f58a4d749daf
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 83ce8b8fe31a35e04c23c316ead5848aec79ec42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="generics-in-the-net-framework-class-library-c-programming-guide"></a><span data-ttu-id="00f58-102">.NET Framework 类库中的泛型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="00f58-102">Generics in the .NET Framework Class Library (C# Programming Guide)</span></span>
<span data-ttu-id="00f58-103">.NET Framework 类库的版本 2.0 提供了新的命名空间 <xref:System.Collections.Generic>，其中包含几个随时可用的泛型集合类和关联接口。</span><span class="sxs-lookup"><span data-stu-id="00f58-103">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which includes several ready-to-use generic collection classes and associated interfaces.</span></span> <span data-ttu-id="00f58-104">其他命名空间，如 <xref:System>，也提供新的泛型接口，例如 <xref:System.IComparable%601>。</span><span class="sxs-lookup"><span data-stu-id="00f58-104">Other namespaces, such as <xref:System>, also provide new generic interfaces such as <xref:System.IComparable%601>.</span></span> <span data-ttu-id="00f58-105">相比早期版本的 .NET Framework 提供的非泛型集合类，这些类和接口更高效且类型更安全。</span><span class="sxs-lookup"><span data-stu-id="00f58-105">These classes and interfaces are more efficient and type-safe than the non-generic collection classes provided in earlier releases of the .NET Framework.</span></span> <span data-ttu-id="00f58-106">在设计和实现自己的自定义集合类之前，请考虑是否可使用 .NET Framework 类库中提供的其中一个类，或从中派生类。</span><span class="sxs-lookup"><span data-stu-id="00f58-106">Before designing and implementing your own custom collection classes, consider whether you can use or derive a class from one of the classes provided in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f58-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00f58-107">See Also</span></span>  
 [<span data-ttu-id="00f58-108">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="00f58-108">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="00f58-109">何时使用泛型集合</span><span class="sxs-lookup"><span data-stu-id="00f58-109">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)  
 [<span data-ttu-id="00f58-110">集合和数据结构</span><span class="sxs-lookup"><span data-stu-id="00f58-110">Collections and Data Structures</span></span>](../../../standard/collections/index.md)  
 [<span data-ttu-id="00f58-111">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="00f58-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
