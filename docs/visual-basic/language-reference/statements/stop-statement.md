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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957623"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="0f542-102">Stop 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f542-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="0f542-103">挂起执行。</span><span class="sxs-lookup"><span data-stu-id="0f542-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f542-104">语法</span><span class="sxs-lookup"><span data-stu-id="0f542-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="0f542-105">备注</span><span class="sxs-lookup"><span data-stu-id="0f542-105">Remarks</span></span>  
 <span data-ttu-id="0f542-106">您可以在`Stop`过程中的任何位置放置语句来挂起执行。</span><span class="sxs-lookup"><span data-stu-id="0f542-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="0f542-107">`Stop`使用语句与在代码中设置断点类似。</span><span class="sxs-lookup"><span data-stu-id="0f542-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="0f542-108">语句暂停执行, 但与此`End`不同, 它不会关闭任何文件或清除任何变量, 除非在已编译的可执行 (.exe) 文件中遇到。 `Stop`</span><span class="sxs-lookup"><span data-stu-id="0f542-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f542-109">如果在集成开发环境 (IDE) 外部运行的代码中遇到语句,则将调用调试器。`Stop`</span><span class="sxs-lookup"><span data-stu-id="0f542-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="0f542-110">无论代码是在调试模式下编译还是在发布模式下编译, 都是如此。</span><span class="sxs-lookup"><span data-stu-id="0f542-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f542-111">示例</span><span class="sxs-lookup"><span data-stu-id="0f542-111">Example</span></span>  
 <span data-ttu-id="0f542-112">此示例使用`Stop`语句`For...Next`通过循环挂起每个迭代的执行。</span><span class="sxs-lookup"><span data-stu-id="0f542-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="0f542-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f542-113">See also</span></span>

- [<span data-ttu-id="0f542-114">End 语句</span><span class="sxs-lookup"><span data-stu-id="0f542-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
