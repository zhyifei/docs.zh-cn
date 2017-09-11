---
title: "[] 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '[]_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
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
ms.openlocfilehash: b49d41af0dd4dc34b1b74c62ce8779aa31d69f77
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="df925-102">[] 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="df925-102">[] Operator (C# Reference)</span></span>
<span data-ttu-id="df925-103">方括号 (`[]`) 可用于数组、索引器和属性。</span><span class="sxs-lookup"><span data-stu-id="df925-103">Square brackets (`[]`) are used for arrays, indexers, and attributes.</span></span> <span data-ttu-id="df925-104">还可用于指针。</span><span class="sxs-lookup"><span data-stu-id="df925-104">They can also be used with pointers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df925-105">备注</span><span class="sxs-lookup"><span data-stu-id="df925-105">Remarks</span></span>  
 <span data-ttu-id="df925-106">数组类型是后接 `[]` 的类型：</span><span class="sxs-lookup"><span data-stu-id="df925-106">An array type is a type followed by `[]`:</span></span>  
  
 <span data-ttu-id="df925-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="df925-107">[!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="df925-108">若要访问数组的元素，请使用方括号将所需元素的索引括起来：</span><span class="sxs-lookup"><span data-stu-id="df925-108">To access an element of an array, the index of the desired element is enclosed in brackets:</span></span>  
  
 <span data-ttu-id="df925-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="df925-109">[!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="df925-110">如果数组索引超出范围，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="df925-110">An exception is thrown if an array index is out of range.</span></span>  
  
 <span data-ttu-id="df925-111">不能重载数组索引运算符；但类型可以定义采用一个或多个参数的索引器和属性。</span><span class="sxs-lookup"><span data-stu-id="df925-111">The array indexing operator cannot be overloaded; however, types can define indexers, and properties that take one or more parameters.</span></span> <span data-ttu-id="df925-112">索引器参数括在方括号内，这一点与数组索引类似，但可以将索引器参数声明为任何类型，这一点与数组索引不同，后者必须为整型。</span><span class="sxs-lookup"><span data-stu-id="df925-112">Indexer parameters are enclosed in square brackets, just like array indexes, but indexer parameters can be declared to be of any type, unlike array indexes, which must be integral.</span></span>  
  
 <span data-ttu-id="df925-113">例如，.NET Framework 定义 `Hashtable` 类型，该类型将任意类型的键和值关联在一起：</span><span class="sxs-lookup"><span data-stu-id="df925-113">For example, the .NET Framework defines a `Hashtable` type that associates keys and values of arbitrary type:</span></span>  
  
 <span data-ttu-id="df925-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="df925-114">[!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="df925-115">方括号还用于指定[属性](../../../csharp/programming-guide/concepts/attributes/index.md)：</span><span class="sxs-lookup"><span data-stu-id="df925-115">Square brackets are also used to specify [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md):</span></span>  
  
 <span data-ttu-id="df925-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="df925-116">[!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="df925-117">可以使用方括号来指定指针索引：</span><span class="sxs-lookup"><span data-stu-id="df925-117">You can use square brackets to index off a pointer:</span></span>  
  
 <span data-ttu-id="df925-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="df925-118">[!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="df925-119">不执行边界检查。</span><span class="sxs-lookup"><span data-stu-id="df925-119">No bounds checking is performed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="df925-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="df925-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df925-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="df925-121">See Also</span></span>  
 <span data-ttu-id="df925-122">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="df925-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="df925-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="df925-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="df925-124">[C# 运算符](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="df925-124">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="df925-125">[数组](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="df925-125">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 <span data-ttu-id="df925-126">[索引器](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="df925-126">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="df925-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="df925-127">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="df925-128">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="df925-128">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)

