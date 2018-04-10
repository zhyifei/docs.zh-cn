---
title: object（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0fcced75d3a86fd700e642e48b7e325e554cae53
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-c-reference"></a><span data-ttu-id="29067-102">object（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="29067-102">object (C# Reference)</span></span>
<span data-ttu-id="29067-103">`object` 类型是 .NET Framework 中 <xref:System.Object> 的别名。</span><span class="sxs-lookup"><span data-stu-id="29067-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="29067-104">在 C# 的统一类型系统中，所有类型（预定义类型、用户定义类型、引用类型和值类型）都是直接或间接从 <xref:System.Object> 继承的。</span><span class="sxs-lookup"><span data-stu-id="29067-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="29067-105">可以将任何类型的值赋给 `object` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="29067-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="29067-106">将值类型的变量转换为对象的过程称为*装箱*。</span><span class="sxs-lookup"><span data-stu-id="29067-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="29067-107">将对象类型的变量转换为值类型的过程称为*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="29067-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="29067-108">有关详细信息，请参阅[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)。</span><span class="sxs-lookup"><span data-stu-id="29067-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29067-109">示例</span><span class="sxs-lookup"><span data-stu-id="29067-109">Example</span></span>  
 <span data-ttu-id="29067-110">下面的示例演示 `object` 类型的变量如何接受任何数据类型的值，以及 `object` 类型的变量如何在 .NET Framework 中使用 <xref:System.Object> 的方法。</span><span class="sxs-lookup"><span data-stu-id="29067-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="29067-111">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="29067-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="29067-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29067-112">See Also</span></span>  
 [<span data-ttu-id="29067-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="29067-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="29067-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="29067-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="29067-115">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="29067-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="29067-116">引用类型</span><span class="sxs-lookup"><span data-stu-id="29067-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="29067-117">值类型</span><span class="sxs-lookup"><span data-stu-id="29067-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
