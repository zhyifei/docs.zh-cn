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
ms.openlocfilehash: 590ac27ebab881353a69077aabdf7a2def3396a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967837"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="7004b-102">Stop 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7004b-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="7004b-103">挂起执行。</span><span class="sxs-lookup"><span data-stu-id="7004b-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7004b-104">语法</span><span class="sxs-lookup"><span data-stu-id="7004b-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="7004b-105">备注</span><span class="sxs-lookup"><span data-stu-id="7004b-105">Remarks</span></span>  
 <span data-ttu-id="7004b-106">可以将放置`Stop`语句暂停执行的过程中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="7004b-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="7004b-107">使用`Stop`语句是类似于在代码中设置断点。</span><span class="sxs-lookup"><span data-stu-id="7004b-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="7004b-108">`Stop`语句将暂停执行，但不同于`End`，它不会关闭任何文件或清除任何变量，除非遇到编译可执行文件 (.exe) 文件中。</span><span class="sxs-lookup"><span data-stu-id="7004b-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7004b-109">如果`Stop`语句遇到在集成的开发环境 (IDE) 外部运行的代码中，将调用调试器。</span><span class="sxs-lookup"><span data-stu-id="7004b-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="7004b-110">这是无论代码是否已在调试版本还是发布模式下进行编译，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="7004b-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7004b-111">示例</span><span class="sxs-lookup"><span data-stu-id="7004b-111">Example</span></span>  
 <span data-ttu-id="7004b-112">此示例使用`Stop`语句暂停执行以便每个循环访问`For...Next`循环。</span><span class="sxs-lookup"><span data-stu-id="7004b-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="7004b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="7004b-113">See also</span></span>
- [<span data-ttu-id="7004b-114">End 语句</span><span class="sxs-lookup"><span data-stu-id="7004b-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
