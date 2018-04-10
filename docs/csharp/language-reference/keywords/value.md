---
title: value（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2501bc8964ed76534dba6c7cc519e095c57cb898
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="value-c-reference"></a><span data-ttu-id="f82a8-102">value（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f82a8-102">value (C# Reference)</span></span>
<span data-ttu-id="f82a8-103">上下文关键字 `value` 用在普通属性声明的 set 访问器中。</span><span class="sxs-lookup"><span data-stu-id="f82a8-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="f82a8-104">此关键字类似于方法的输入参数。</span><span class="sxs-lookup"><span data-stu-id="f82a8-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="f82a8-105">关键字 `value` 引用客户端代码尝试分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="f82a8-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="f82a8-106">在以下示例中，`MyDerivedClass` 有一个名为 `Name` 的属性，该属性使用 `value` 参数向支持字段 `name` 分配新字符串。</span><span class="sxs-lookup"><span data-stu-id="f82a8-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="f82a8-107">从客户端代码的角度来看，该操作写作一个简单的赋值语句。</span><span class="sxs-lookup"><span data-stu-id="f82a8-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="f82a8-108">有关 `value` 用法的详细信息，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="f82a8-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f82a8-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f82a8-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f82a8-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f82a8-110">See Also</span></span>  
 [<span data-ttu-id="f82a8-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f82a8-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f82a8-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f82a8-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f82a8-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f82a8-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
