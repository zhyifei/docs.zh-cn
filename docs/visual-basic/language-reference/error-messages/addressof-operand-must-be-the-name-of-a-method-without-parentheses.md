---
title: “AddressOf”操作数必须是方法名（不带括号）
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: af1ce858108785fa4dac6352c9e80531e86fbb23
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813959"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="f71e9-102">“AddressOf”操作数必须是方法名（不带括号）</span><span class="sxs-lookup"><span data-stu-id="f71e9-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="f71e9-103">`AddressOf` 运算符创建引用特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="f71e9-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="f71e9-104">语法如下所示。</span><span class="sxs-lookup"><span data-stu-id="f71e9-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="f71e9-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="f71e9-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="f71e9-106">插入参数后面的两边的括号`AddressOf`，当不需要。</span><span class="sxs-lookup"><span data-stu-id="f71e9-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="f71e9-107">**错误 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="f71e9-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f71e9-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f71e9-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="f71e9-109">删除后面的参数两边的括号`AddressOf`。</span><span class="sxs-lookup"><span data-stu-id="f71e9-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="f71e9-110">请确保参数是方法名称。</span><span class="sxs-lookup"><span data-stu-id="f71e9-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f71e9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f71e9-111">See also</span></span>

- [<span data-ttu-id="f71e9-112">AddressOf 运算符</span><span class="sxs-lookup"><span data-stu-id="f71e9-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="f71e9-113">委托</span><span class="sxs-lookup"><span data-stu-id="f71e9-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
