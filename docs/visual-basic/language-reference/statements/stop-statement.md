---
title: Stop 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599130"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="717e5-102">Stop 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="717e5-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="717e5-103">挂起执行。</span><span class="sxs-lookup"><span data-stu-id="717e5-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717e5-104">语法</span><span class="sxs-lookup"><span data-stu-id="717e5-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="717e5-105">备注</span><span class="sxs-lookup"><span data-stu-id="717e5-105">Remarks</span></span>  
 <span data-ttu-id="717e5-106">你可以将放置`Stop`语句暂停执行的过程中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="717e5-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="717e5-107">使用`Stop`语句是相似的代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="717e5-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="717e5-108">`Stop`语句挂起执行，但与`End`，它不会关闭任何文件或清除任何变量，除非在已编译可执行文件 (.exe) 文件中遇到。</span><span class="sxs-lookup"><span data-stu-id="717e5-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="717e5-109">如果`Stop`在集成的开发环境 (IDE) 外部运行的代码中遇到语句，将调用调试器。</span><span class="sxs-lookup"><span data-stu-id="717e5-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="717e5-110">无论是如此代码是否在调试版本还是发布模式下进行编译。</span><span class="sxs-lookup"><span data-stu-id="717e5-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="717e5-111">示例</span><span class="sxs-lookup"><span data-stu-id="717e5-111">Example</span></span>  
 <span data-ttu-id="717e5-112">此示例使用`Stop`语句暂停执行以便每个循环访问`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="717e5-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="717e5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="717e5-113">See Also</span></span>  
 [<span data-ttu-id="717e5-114">End 语句</span><span class="sxs-lookup"><span data-stu-id="717e5-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
