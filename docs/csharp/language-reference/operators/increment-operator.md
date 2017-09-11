---
title: "++ 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f481dbe2437495b109d6d41cd24c8b4bb5b6a5b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="72fd5-102">++ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="72fd5-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="72fd5-103">递增运算符 (`++`) 按 1 递增其操作数。</span><span class="sxs-lookup"><span data-stu-id="72fd5-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="72fd5-104">递增运算符可以在其操作数之前或之后出现： `++variable` 和 `variable++`。</span><span class="sxs-lookup"><span data-stu-id="72fd5-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72fd5-105">备注</span><span class="sxs-lookup"><span data-stu-id="72fd5-105">Remarks</span></span>  
 <span data-ttu-id="72fd5-106">第一个窗体是前缀递增操作。</span><span class="sxs-lookup"><span data-stu-id="72fd5-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="72fd5-107">操作的结果是操作数递增后的值。</span><span class="sxs-lookup"><span data-stu-id="72fd5-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="72fd5-108">第二个窗体是后缀递增操作。</span><span class="sxs-lookup"><span data-stu-id="72fd5-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="72fd5-109">操作的结果是操作数递增前的值。</span><span class="sxs-lookup"><span data-stu-id="72fd5-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="72fd5-110">数值和枚举类型具有预定义的递增运算符。</span><span class="sxs-lookup"><span data-stu-id="72fd5-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="72fd5-111">用户定义的类型可以重载 `++` 运算符。</span><span class="sxs-lookup"><span data-stu-id="72fd5-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="72fd5-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="72fd5-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72fd5-113">示例</span><span class="sxs-lookup"><span data-stu-id="72fd5-113">Example</span></span>  
 <span data-ttu-id="72fd5-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="72fd5-114">[!code-cs[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72fd5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72fd5-115">See Also</span></span>  
 <span data-ttu-id="72fd5-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="72fd5-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="72fd5-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="72fd5-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="72fd5-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="72fd5-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

