---
title: Alias 子句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="75e7d-102">Alias 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75e7d-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="75e7d-103">指示外部过程其 DLL 中具有另一个名称。</span><span class="sxs-lookup"><span data-stu-id="75e7d-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75e7d-104">备注</span><span class="sxs-lookup"><span data-stu-id="75e7d-104">Remarks</span></span>  
 <span data-ttu-id="75e7d-105">`Alias`关键字可在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="75e7d-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="75e7d-106">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="75e7d-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="75e7d-107">在下面的示例中，`Alias`关键字用于提供 advapi32.dll 中的函数名称`GetUserNameA`，则该`getUserName`代替了此示例中使用。</span><span class="sxs-lookup"><span data-stu-id="75e7d-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="75e7d-108">函数`getUserName`sub 中调用`getUser`，它会显示当前用户的名称。</span><span class="sxs-lookup"><span data-stu-id="75e7d-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="75e7d-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75e7d-109">See Also</span></span>  
 [<span data-ttu-id="75e7d-110">关键字</span><span class="sxs-lookup"><span data-stu-id="75e7d-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
