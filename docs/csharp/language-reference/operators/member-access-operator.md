---
title: "。 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ._CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
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
ms.openlocfilehash: fdc7c1821548509f3a3750aef2836c034f7aa53b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="702a4-103">。</span><span class="sxs-lookup"><span data-stu-id="702a4-103">.</span></span> <span data-ttu-id="702a4-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="702a4-104">Operator (C# Reference)</span></span>
<span data-ttu-id="702a4-105">点运算符 (`.`) 用于成员访问。</span><span class="sxs-lookup"><span data-stu-id="702a4-105">The dot operator (`.`) is used for member access.</span></span> <span data-ttu-id="702a4-106">点运算符指定类型或命名空间的成员。</span><span class="sxs-lookup"><span data-stu-id="702a4-106">The dot operator specifies a member of a type or namespace.</span></span> <span data-ttu-id="702a4-107">例如，点运算符用于访问 .NET Framework 类库中的特定方法：</span><span class="sxs-lookup"><span data-stu-id="702a4-107">For example, the dot operator is used to access specific methods within the .NET Framework class libraries:</span></span>  
  
 <span data-ttu-id="702a4-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-108">[!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="702a4-109">例如，请考虑以下类：</span><span class="sxs-lookup"><span data-stu-id="702a4-109">For example, consider the following class:</span></span>  
  
 <span data-ttu-id="702a4-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-110">[!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_2.cs)]</span></span>  
  
 <span data-ttu-id="702a4-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-111">[!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_3.cs)]</span></span>  
  
 <span data-ttu-id="702a4-112">变量 `s` 具有两个成员（`a` 和 `b`）；若要对其进行访问，请使用点运算符：</span><span class="sxs-lookup"><span data-stu-id="702a4-112">The variable `s` has two members, `a` and `b`; to access them, use the dot operator:</span></span>  
  
 <span data-ttu-id="702a4-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-113">[!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_4.cs)]</span></span>  
  
 <span data-ttu-id="702a4-114">点还用于构成限定名称，即为指定它们所属的命名空间或接口等的名称。</span><span class="sxs-lookup"><span data-stu-id="702a4-114">The dot is also used to form qualified names, which are names that specify the namespace or interface, for example, to which they belong.</span></span>  
  
 <span data-ttu-id="702a4-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-115">[!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_5.cs)]</span></span>  
  
 <span data-ttu-id="702a4-116">using 指令使某些名称限定变成可选：</span><span class="sxs-lookup"><span data-stu-id="702a4-116">The using directive makes some name qualification optional:</span></span>  
  
 <span data-ttu-id="702a4-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-117">[!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_6.cs)]</span></span>  
  
 <span data-ttu-id="702a4-118">但如果标识符不明确，则必须对其进行限定：</span><span class="sxs-lookup"><span data-stu-id="702a4-118">But when an identifier is ambiguous, it must be qualified:</span></span>  
  
 <span data-ttu-id="702a4-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="702a4-119">[!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/CSharp/member-access-operator_7.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="702a4-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="702a4-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="702a4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="702a4-121">See Also</span></span>  
 <span data-ttu-id="702a4-122">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="702a4-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="702a4-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="702a4-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="702a4-124">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="702a4-124">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

