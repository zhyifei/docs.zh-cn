---
title: "-&gt; 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ->_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
caps.latest.revision: 19
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
ms.openlocfilehash: f42135e43bdfc58ee64fd3465074b3f8791f8ada
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="d4b0c-102">-&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d4b0c-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="d4b0c-103">`->` 运算符将取消指针引用与成员访问结合起来。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4b0c-104">备注</span><span class="sxs-lookup"><span data-stu-id="d4b0c-104">Remarks</span></span>  
 <span data-ttu-id="d4b0c-105">形式如下的表达式，</span><span class="sxs-lookup"><span data-stu-id="d4b0c-105">An expression of the form,</span></span>  
  
```  
x->y  
```  
  
 <span data-ttu-id="d4b0c-106">（其中 `x` 是 `T*` 类型的指针，`y` 属于 `T`）等效于</span><span class="sxs-lookup"><span data-stu-id="d4b0c-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```  
(*x).y  
```  
  
 <span data-ttu-id="d4b0c-107">`->` 运算符仅可用于标记为[不安全](../../../csharp/language-reference/keywords/unsafe.md)的代码中。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="d4b0c-108">不能重载 `->` 运算符。</span><span class="sxs-lookup"><span data-stu-id="d4b0c-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4b0c-109">示例</span><span class="sxs-lookup"><span data-stu-id="d4b0c-109">Example</span></span>  
 <span data-ttu-id="d4b0c-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d4b0c-110">[!code-cs[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b0c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4b0c-111">See Also</span></span>  
 <span data-ttu-id="d4b0c-112">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4b0c-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d4b0c-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d4b0c-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="d4b0c-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d4b0c-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

