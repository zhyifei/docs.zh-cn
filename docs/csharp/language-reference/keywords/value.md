---
title: "value（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- value_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 012cf622091687996fec477a8b5b821b190bbc29
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="value-c-reference"></a><span data-ttu-id="d0769-102">value（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d0769-102">value (C# Reference)</span></span>
<span data-ttu-id="d0769-103">上下文关键字 `value` 用在普通属性声明的 set 访问器中。</span><span class="sxs-lookup"><span data-stu-id="d0769-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="d0769-104">此关键字类似于方法的输入参数。</span><span class="sxs-lookup"><span data-stu-id="d0769-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="d0769-105">关键字 `value` 引用客户端代码尝试分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="d0769-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="d0769-106">在以下示例中，`MyDerivedClass` 有一个名为 `Name` 的属性，该属性使用 `value` 参数向支持字段 `name` 分配新字符串。</span><span class="sxs-lookup"><span data-stu-id="d0769-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="d0769-107">从客户端代码的角度来看，该操作写作一个简单的赋值语句。</span><span class="sxs-lookup"><span data-stu-id="d0769-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 <span data-ttu-id="d0769-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0769-108">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]</span></span>  
  
 <span data-ttu-id="d0769-109">有关 `value` 用法的详细信息，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="d0769-109">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d0769-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="d0769-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0769-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0769-111">See Also</span></span>  
 <span data-ttu-id="d0769-112">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0769-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d0769-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d0769-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="d0769-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="d0769-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

