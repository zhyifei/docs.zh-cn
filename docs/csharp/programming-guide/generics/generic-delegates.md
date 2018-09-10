---
title: 泛型委托（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 7596ace0ea404cc345d73c0979fa7bd03a26b047
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857531"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="4314e-102">泛型委托（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4314e-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="4314e-103">[委托](../../../csharp/language-reference/keywords/delegate.md)可以定义它自己的类型参数。</span><span class="sxs-lookup"><span data-stu-id="4314e-103">A [delegate](../../../csharp/language-reference/keywords/delegate.md) can define its own type parameters.</span></span> <span data-ttu-id="4314e-104">引用泛型委托的代码可以指定类型参数以创建封闭式构造类型，就像实例化泛型类或调用泛型方法一样，如以下示例中所示：</span><span class="sxs-lookup"><span data-stu-id="4314e-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_1.cs)]  
  
 <span data-ttu-id="4314e-105">C# 2.0 版具有一种称为方法组转换的新功能，适用于具体委托类型和泛型委托类型，使你能够使用此简化语法编写上一行：</span><span class="sxs-lookup"><span data-stu-id="4314e-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_2.cs)]  
  
 <span data-ttu-id="4314e-106">在泛型类中定义的委托可以用类方法使用的相同方式来使用泛型类类型参数。</span><span class="sxs-lookup"><span data-stu-id="4314e-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_3.cs)]  
  
 <span data-ttu-id="4314e-107">引用委托的代码必须指定包含类的类型参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4314e-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_4.cs)]  
  
 <span data-ttu-id="4314e-108">根据典型设计模式定义事件时，泛型委托特别有用，因为发件人参数可以为强类型，无需在它和 <xref:System.Object> 之间强制转换。</span><span class="sxs-lookup"><span data-stu-id="4314e-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-delegates_5.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="4314e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4314e-109">See Also</span></span>

- <xref:System.Collections.Generic>  
- [<span data-ttu-id="4314e-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4314e-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="4314e-111">泛型介绍</span><span class="sxs-lookup"><span data-stu-id="4314e-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
- [<span data-ttu-id="4314e-112">泛型方法</span><span class="sxs-lookup"><span data-stu-id="4314e-112">Generic Methods</span></span>](../../../csharp/programming-guide/generics/generic-methods.md)  
- [<span data-ttu-id="4314e-113">泛型类</span><span class="sxs-lookup"><span data-stu-id="4314e-113">Generic Classes</span></span>](../../../csharp/programming-guide/generics/generic-classes.md)  
- [<span data-ttu-id="4314e-114">泛型接口</span><span class="sxs-lookup"><span data-stu-id="4314e-114">Generic Interfaces</span></span>](../../../csharp/programming-guide/generics/generic-interfaces.md)  
- [<span data-ttu-id="4314e-115">委托</span><span class="sxs-lookup"><span data-stu-id="4314e-115">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
- [<span data-ttu-id="4314e-116">泛型</span><span class="sxs-lookup"><span data-stu-id="4314e-116">Generics</span></span>](~/docs/standard/generics/index.md)
