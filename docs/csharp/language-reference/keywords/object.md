---
title: "object（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
dev_langs:
- CSharp
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
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
ms.openlocfilehash: 744debc51f68cc52f03bce09c9f276a66ae085e1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="object-c-reference"></a><span data-ttu-id="10d38-102">object（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="10d38-102">object (C# Reference)</span></span>
<span data-ttu-id="10d38-103">`object` 类型是 .NET Framework 中 <xref:System.Object> 的别名。</span><span class="sxs-lookup"><span data-stu-id="10d38-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="10d38-104">在 C# 的统一类型系统中，所有类型（预定义类型、用户定义类型、引用类型和值类型）都是直接或间接从 <xref:System.Object> 继承的。</span><span class="sxs-lookup"><span data-stu-id="10d38-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="10d38-105">可以将任何类型的值赋给 `object` 类型的变量。</span><span class="sxs-lookup"><span data-stu-id="10d38-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="10d38-106">将值类型的变量转换为对象的过程称为*装箱*。</span><span class="sxs-lookup"><span data-stu-id="10d38-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="10d38-107">将对象类型的变量转换为值类型的过程称为*取消装箱*。</span><span class="sxs-lookup"><span data-stu-id="10d38-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="10d38-108">有关详细信息，请参阅[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)。</span><span class="sxs-lookup"><span data-stu-id="10d38-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10d38-109">示例</span><span class="sxs-lookup"><span data-stu-id="10d38-109">Example</span></span>  
 <span data-ttu-id="10d38-110">下面的示例演示 `object` 类型的变量如何接受任何数据类型的值，以及 `object` 类型的变量如何在 .NET Framework 中使用 <xref:System.Object> 的方法。</span><span class="sxs-lookup"><span data-stu-id="10d38-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 <span data-ttu-id="10d38-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="10d38-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="10d38-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="10d38-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10d38-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="10d38-113">See Also</span></span>  
 <span data-ttu-id="10d38-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d38-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="10d38-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d38-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="10d38-116">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d38-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="10d38-117">[引用类型](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="10d38-117">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 [<span data-ttu-id="10d38-118">值类型</span><span class="sxs-lookup"><span data-stu-id="10d38-118">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

