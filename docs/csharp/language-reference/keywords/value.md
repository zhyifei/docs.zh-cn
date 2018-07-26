---
title: value（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- value_CSharpKeyword
helpviewer_keywords:
- value keyword [C#]
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
ms.openlocfilehash: c8f808540385552f6222566f23251f6cbd6e86df
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37959383"
---
# <a name="value-c-reference"></a><span data-ttu-id="c9776-102">value（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c9776-102">value (C# Reference)</span></span>
<span data-ttu-id="c9776-103">上下文关键字 `value` 用在普通属性声明的 set 访问器中。</span><span class="sxs-lookup"><span data-stu-id="c9776-103">The contextual keyword `value` is used in the set accessor in ordinary property declarations.</span></span> <span data-ttu-id="c9776-104">此关键字类似于方法的输入参数。</span><span class="sxs-lookup"><span data-stu-id="c9776-104">It is similar to an input parameter on a method.</span></span> <span data-ttu-id="c9776-105">关键字 `value` 引用客户端代码尝试分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="c9776-105">The word `value` references the value that client code is attempting to assign to the property.</span></span> <span data-ttu-id="c9776-106">在以下示例中，`MyDerivedClass` 有一个名为 `Name` 的属性，该属性使用 `value` 参数向支持字段 `name` 分配新字符串。</span><span class="sxs-lookup"><span data-stu-id="c9776-106">In the following example, `MyDerivedClass` has a property called `Name` that uses the `value` parameter to assign a new string to the backing field `name`.</span></span> <span data-ttu-id="c9776-107">从客户端代码的角度来看，该操作写作一个简单的赋值语句。</span><span class="sxs-lookup"><span data-stu-id="c9776-107">From the point of view of client code, the operation is written as a simple assignment.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 <span data-ttu-id="c9776-108">有关 `value` 用法的详细信息，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c9776-108">For more information about the use of `value`, see [Properties](../../../csharp/programming-guide/classes-and-structs/properties.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c9776-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c9776-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c9776-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9776-110">See Also</span></span>  
 [<span data-ttu-id="c9776-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c9776-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c9776-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c9776-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c9776-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c9776-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
