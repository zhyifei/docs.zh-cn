---
title: -&gt; 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: fb95e508ce1339868723bcc3178851e8c1355c1f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45609512"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="a5b43-102">-&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a5b43-102">-&gt; Operator (C# Reference)</span></span>
<span data-ttu-id="a5b43-103">`->` 运算符将取消指针引用与成员访问结合起来。</span><span class="sxs-lookup"><span data-stu-id="a5b43-103">The `->` operator combines pointer dereferencing and member access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5b43-104">备注</span><span class="sxs-lookup"><span data-stu-id="a5b43-104">Remarks</span></span>  
 <span data-ttu-id="a5b43-105">形式如下的表达式，</span><span class="sxs-lookup"><span data-stu-id="a5b43-105">An expression of the form,</span></span>  
  
```csharp  
x->y  
```  
  
 <span data-ttu-id="a5b43-106">（其中 `x` 是 `T*` 类型的指针，`y` 属于 `T`）等效于</span><span class="sxs-lookup"><span data-stu-id="a5b43-106">(where `x` is a pointer of type `T*` and `y` is a member of `T`) is equivalent to,</span></span>  
  
```csharp  
(*x).y  
```  
  
 <span data-ttu-id="a5b43-107">`->` 运算符仅可用于标记为[不安全](../../../csharp/language-reference/keywords/unsafe.md)的代码中。</span><span class="sxs-lookup"><span data-stu-id="a5b43-107">The `->` operator can be used only in code that is marked as [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
 <span data-ttu-id="a5b43-108">不能重载 `->` 运算符。</span><span class="sxs-lookup"><span data-stu-id="a5b43-108">The `->` operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5b43-109">示例</span><span class="sxs-lookup"><span data-stu-id="a5b43-109">Example</span></span>  
 [!code-csharp[csRefOperators#15](../../../csharp/language-reference/operators/codesnippet/CSharp/dereference-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a5b43-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5b43-110">See Also</span></span>

- [<span data-ttu-id="a5b43-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a5b43-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="a5b43-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a5b43-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a5b43-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="a5b43-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
