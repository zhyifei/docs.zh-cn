---
title: “AddressOf”操作数必须是方法名（不带括号）
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323819"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="69cda-102">“AddressOf”操作数必须是方法名（不带括号）</span><span class="sxs-lookup"><span data-stu-id="69cda-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="69cda-103">`AddressOf` 运算符创建引用特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="69cda-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="69cda-104">语法如下所示。</span><span class="sxs-lookup"><span data-stu-id="69cda-104">The syntax is as follows.</span></span>  
  
 `AddressOf` `procedurename`  
  
 <span data-ttu-id="69cda-105">插入参数后面的两边的括号`AddressOf`，当不需要。</span><span class="sxs-lookup"><span data-stu-id="69cda-105">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="69cda-106">**错误 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="69cda-106">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69cda-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="69cda-107">To correct this error</span></span>  
  
1. <span data-ttu-id="69cda-108">删除后面的参数两边的括号`AddressOf`。</span><span class="sxs-lookup"><span data-stu-id="69cda-108">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2. <span data-ttu-id="69cda-109">请确保参数是方法名称。</span><span class="sxs-lookup"><span data-stu-id="69cda-109">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cda-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="69cda-110">See also</span></span>

- [<span data-ttu-id="69cda-111">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="69cda-111">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="69cda-112">委托</span><span class="sxs-lookup"><span data-stu-id="69cda-112">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
