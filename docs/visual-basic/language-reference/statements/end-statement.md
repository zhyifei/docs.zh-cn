---
title: "End 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b692409f2895f5e9b713c57fc35ff2def40bce75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="end-statement"></a><span data-ttu-id="b8416-102">End 语句</span><span class="sxs-lookup"><span data-stu-id="b8416-102">End Statement</span></span>
<span data-ttu-id="b8416-103">会立即终止执行。</span><span class="sxs-lookup"><span data-stu-id="b8416-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8416-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8416-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="b8416-105">备注</span><span class="sxs-lookup"><span data-stu-id="b8416-105">Remarks</span></span>  
 <span data-ttu-id="b8416-106">你可以将放置`End`以强制整个应用程序停止运行过程中的任意位置的语句。</span><span class="sxs-lookup"><span data-stu-id="b8416-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="b8416-107">`End`关闭使用打开的任何文件`Open`语句，并清除应用程序的所有变量。</span><span class="sxs-lookup"><span data-stu-id="b8416-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="b8416-108">应用程序关闭一旦没有保留对其对象的引用其他程序并没有其代码运行。</span><span class="sxs-lookup"><span data-stu-id="b8416-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8416-109">`End`语句突然，停止执行代码并不会调用`Dispose`或`Finalize`方法或任何其他 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="b8416-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="b8416-110">持有的其他程序对象引用将会失效。</span><span class="sxs-lookup"><span data-stu-id="b8416-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="b8416-111">如果`End`内遇到语句`Try`或`Catch`块中，控件不会将传递给相应`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="b8416-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="b8416-112">`Stop`语句挂起执行，但与`End`，它不会关闭任何文件或清除任何变量，除非在已编译可执行文件 (.exe) 文件中遇到。</span><span class="sxs-lookup"><span data-stu-id="b8416-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="b8416-113">因为`End`终止而不顾及应用程序的任何可能已打开的资源，你应尝试彻底关闭然后再使用它。</span><span class="sxs-lookup"><span data-stu-id="b8416-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="b8416-114">例如，如果应用程序的任何打开的窗体，你应该先关闭这些控件达到`End`语句。</span><span class="sxs-lookup"><span data-stu-id="b8416-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="b8416-115">应使用`End`尽量少，且仅当你需要立即停止。</span><span class="sxs-lookup"><span data-stu-id="b8416-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="b8416-116">终止过程的正常方式 ([Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)和[退出语句](../../../visual-basic/language-reference/statements/exit-statement.md)) 不仅完全关闭过程，但还为调用的代码提供彻底关闭的机会。</span><span class="sxs-lookup"><span data-stu-id="b8416-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="b8416-117">控制台应用程序，例如，可以只需`Return`从`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="b8416-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b8416-118">`End`语句也会调用<xref:System.Environment.Exit%2A>方法<xref:System.Environment>类<xref:System>命名空间。</span><span class="sxs-lookup"><span data-stu-id="b8416-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="b8416-119"><xref:System.Environment.Exit%2A>你需要具有`UnmanagedCode`权限。</span><span class="sxs-lookup"><span data-stu-id="b8416-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="b8416-120">如果你不希望这样做，<xref:System.Security.SecurityException>发生错误。</span><span class="sxs-lookup"><span data-stu-id="b8416-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="b8416-121">当附加关键字后, 跟[结束\<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)描述的定义的相应过程或块的末尾。</span><span class="sxs-lookup"><span data-stu-id="b8416-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="b8416-122">例如，`End Function`终止的定义`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="b8416-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8416-123">示例</span><span class="sxs-lookup"><span data-stu-id="b8416-123">Example</span></span>  
 <span data-ttu-id="b8416-124">下面的示例使用`End`语句，终止执行代码，如果用户请求它。</span><span class="sxs-lookup"><span data-stu-id="b8416-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="b8416-125">智能设备的开发人员说明</span><span class="sxs-lookup"><span data-stu-id="b8416-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="b8416-126">不支持此语句。</span><span class="sxs-lookup"><span data-stu-id="b8416-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8416-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8416-127">See Also</span></span>  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [<span data-ttu-id="b8416-128">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="b8416-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [<span data-ttu-id="b8416-129">结束\<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="b8416-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
