---
title: "AddressOf 操作数必须是 （不带括号） 方法的名称 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c4ee57896b70d8af1a7bc245bdb45521c2442fea
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="7dbd7-102">AddressOf 操作数必须是 （不带括号） 方法的名称</span><span class="sxs-lookup"><span data-stu-id="7dbd7-102">&#39;AddressOf&#39; operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="7dbd7-103">`AddressOf` 运算符创建引用特定过程的过程委托实例。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="7dbd7-104">语法是，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="7dbd7-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="7dbd7-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="7dbd7-106">插入后面的参数两边的括号`AddressOf`，这里不需要。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="7dbd7-107">**错误 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="7dbd7-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7dbd7-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7dbd7-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="7dbd7-109">删除后面的参数两边的括号`AddressOf`。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="7dbd7-110">请确保该参数的方法名称。</span><span class="sxs-lookup"><span data-stu-id="7dbd7-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dbd7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7dbd7-111">See Also</span></span>  
 <span data-ttu-id="7dbd7-112">[AddressOf 运算符](../../../visual-basic/language-reference/operators/addressof-operator.md) </span><span class="sxs-lookup"><span data-stu-id="7dbd7-112">[AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md) </span></span>  
<span data-ttu-id="7dbd7-113"> [委托](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="7dbd7-113"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>
