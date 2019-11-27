---
title: Alias 子句
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349144"
---
# <a name="alias-clause-visual-basic"></a><span data-ttu-id="199f0-102">Alias 子句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="199f0-102">Alias Clause (Visual Basic)</span></span>
<span data-ttu-id="199f0-103">指示外部过程在其 DLL 中有另一个名称。</span><span class="sxs-lookup"><span data-stu-id="199f0-103">Indicates that an external procedure has another name in its DLL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="199f0-104">备注</span><span class="sxs-lookup"><span data-stu-id="199f0-104">Remarks</span></span>  
 <span data-ttu-id="199f0-105">可以在此上下文中使用 `Alias` 关键字：</span><span class="sxs-lookup"><span data-stu-id="199f0-105">The `Alias` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="199f0-106">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="199f0-106">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="199f0-107">在下面的示例中，`Alias` 关键字用于提供 advapi32.dll 中函数的名称，`GetUserNameA`，该 `getUserName` 用于替代本示例中的。</span><span class="sxs-lookup"><span data-stu-id="199f0-107">In the following example, the `Alias` keyword is used to provide the name of the function in advapi32.dll, `GetUserNameA`, that `getUserName` is used in place of in this example.</span></span> <span data-ttu-id="199f0-108">函数 `getUserName` 在 sub `getUser`中调用，后者显示当前用户的名称。</span><span class="sxs-lookup"><span data-stu-id="199f0-108">Function `getUserName` is called in sub `getUser`, which displays the name of the current user.</span></span>  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="199f0-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="199f0-109">See also</span></span>

- [<span data-ttu-id="199f0-110">关键字</span><span class="sxs-lookup"><span data-stu-id="199f0-110">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
