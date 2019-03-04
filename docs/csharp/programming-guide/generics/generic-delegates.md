---
title: 泛型委托 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 2806eadd2d3f8a4c3e8f001b02b28d35a60daaec
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970145"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="efd98-102">泛型委托（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="efd98-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="efd98-103">[委托](../../../csharp/language-reference/keywords/delegate.md)可以定义它自己的类型参数。</span><span class="sxs-lookup"><span data-stu-id="efd98-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="efd98-104">引用泛型委托的代码可以指定类型参数以创建封闭式构造类型，就像实例化泛型类或调用泛型方法一样，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="efd98-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="efd98-105">C# 2.0 版具有一种称为方法组转换的新功能，适用于具体委托类型和泛型委托类型，使你能够使用此简化语法编写上一行：</span><span class="sxs-lookup"><span data-stu-id="efd98-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="efd98-106">在泛型类中定义的委托可以用类方法使用的相同方式来使用泛型类类型参数。</span><span class="sxs-lookup"><span data-stu-id="efd98-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="efd98-107">引用委托的代码必须指定包含类的类型参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="efd98-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="efd98-108">根据典型设计模式定义事件时，泛型委托特别有用，因为发件人参数可以为强类型，无需在它和 <xref:System.Object> 之间强制转换。</span><span class="sxs-lookup"><span data-stu-id="efd98-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="efd98-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="efd98-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="efd98-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="efd98-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="efd98-111">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="efd98-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
- [<span data-ttu-id="efd98-112">泛型方法</span><span class="sxs-lookup"><span data-stu-id="efd98-112">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)
- [<span data-ttu-id="efd98-113">泛型类</span><span class="sxs-lookup"><span data-stu-id="efd98-113">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)
- [<span data-ttu-id="efd98-114">泛型接口</span><span class="sxs-lookup"><span data-stu-id="efd98-114">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)
- [<span data-ttu-id="efd98-115">委托</span><span class="sxs-lookup"><span data-stu-id="efd98-115">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)
- [<span data-ttu-id="efd98-116">泛型</span><span class="sxs-lookup"><span data-stu-id="efd98-116">Generics</span></span>](~/docs/standard/generics/index.md)
