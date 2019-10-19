---
title: 嵌套函数没有与委托“<delegatename>”兼容的签名。
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: d65c8eab661675c955ff6562098248c04036d6e7
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580653"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a><span data-ttu-id="4ac0c-102">嵌套函数没有与委托 "\<delegatename >" 兼容的签名</span><span class="sxs-lookup"><span data-stu-id="4ac0c-102">Nested function does not have a signature that is compatible with delegate '\<delegatename>'</span></span>

<span data-ttu-id="4ac0c-103">已将 lambda 表达式分配给具有不兼容签名的委托。</span><span class="sxs-lookup"><span data-stu-id="4ac0c-103">A lambda expression has been assigned to a delegate that has an incompatible signature.</span></span> <span data-ttu-id="4ac0c-104">例如，在下面的代码中，委托 `Del` 有两个整数参数。</span><span class="sxs-lookup"><span data-stu-id="4ac0c-104">For example, in the following code, delegate `Del` has two integer parameters.</span></span>

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

<span data-ttu-id="4ac0c-105">如果将带一个自变量的 lambda 表达式声明为类型 `Del`，则会引发此错误：</span><span class="sxs-lookup"><span data-stu-id="4ac0c-105">The error is raised if a lambda expression with one argument is declared as type `Del`:</span></span>

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

<span data-ttu-id="4ac0c-106">**错误 ID：** BC36532</span><span class="sxs-lookup"><span data-stu-id="4ac0c-106">**Error ID:** BC36532</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4ac0c-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4ac0c-107">To correct this error</span></span>

<span data-ttu-id="4ac0c-108">调整委托定义或指定的 lambda 表达式，使签名兼容。</span><span class="sxs-lookup"><span data-stu-id="4ac0c-108">Adjust either the delegate definition or the assigned lambda expression so that the signatures are compatible.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ac0c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ac0c-109">See also</span></span>

- [<span data-ttu-id="4ac0c-110">宽松委托转换</span><span class="sxs-lookup"><span data-stu-id="4ac0c-110">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [<span data-ttu-id="4ac0c-111">Lambda 表达式</span><span class="sxs-lookup"><span data-stu-id="4ac0c-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
