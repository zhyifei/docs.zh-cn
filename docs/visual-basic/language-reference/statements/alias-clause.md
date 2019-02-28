---
title: Alias 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 3b1a66ecfd3c023a12ac62191ca3671a195b45a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978223"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="bf36c-102">Alias 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf36c-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="bf36c-103">指示外部过程在其 DLL 中具有另一个名称。</span><span class="sxs-lookup"><span data-stu-id="bf36c-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf36c-104">备注</span><span class="sxs-lookup"><span data-stu-id="bf36c-104">Remarks</span></span>  
 <span data-ttu-id="bf36c-105">`Alias`关键字可在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="bf36c-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="bf36c-106">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="bf36c-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="bf36c-107">在以下示例中，`Alias`关键字用于提供 advapi32.dll 中的函数的名称`GetUserNameA`，则该`getUserName`来代替此示例中使用。</span><span class="sxs-lookup"><span data-stu-id="bf36c-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="bf36c-108">函数`getUserName`sub 中名为`getUser`，后者将显示当前用户的名称。</span><span class="sxs-lookup"><span data-stu-id="bf36c-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="bf36c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf36c-109">See also</span></span>
- [<span data-ttu-id="bf36c-110">关键字</span><span class="sxs-lookup"><span data-stu-id="bf36c-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
