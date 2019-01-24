---
title: End 语句 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: a2c211e5ebfd00a639644243312cbe25f71f4cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593701"
---
# <a name="end-statement"></a><span data-ttu-id="36450-102">End 语句</span><span class="sxs-lookup"><span data-stu-id="36450-102">End Statement</span></span>
<span data-ttu-id="36450-103">立即终止执行。</span><span class="sxs-lookup"><span data-stu-id="36450-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36450-104">语法</span><span class="sxs-lookup"><span data-stu-id="36450-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="36450-105">备注</span><span class="sxs-lookup"><span data-stu-id="36450-105">Remarks</span></span>  
 <span data-ttu-id="36450-106">可以将放置`End`强制停止正在运行的整个应用程序的过程中的任意位置的语句。</span><span class="sxs-lookup"><span data-stu-id="36450-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="36450-107">`End` 关闭打开的任何文件`Open`语句，并清除应用程序的所有变量。</span><span class="sxs-lookup"><span data-stu-id="36450-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="36450-108">在应用程序关闭在没有保存对其对象的引用其他程序并无其代码运行。</span><span class="sxs-lookup"><span data-stu-id="36450-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="36450-109">`End`语句突然停止执行代码并不会调用`Dispose`或`Finalize`方法或任何其他 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="36450-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="36450-110">保留由其他程序的对象引用都将失效。</span><span class="sxs-lookup"><span data-stu-id="36450-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="36450-111">如果`End`语句中遇到`Try`或`Catch`块中，控件不会将传递给相应`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="36450-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="36450-112">`Stop`语句将暂停执行，但不同于`End`，它不会关闭任何文件或清除任何变量，除非遇到编译可执行文件 (.exe) 文件中。</span><span class="sxs-lookup"><span data-stu-id="36450-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="36450-113">因为`End`终止而不顾及应用程序对任何可能处于打开状态的资源，您应尝试彻底关闭然后再使用它。</span><span class="sxs-lookup"><span data-stu-id="36450-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="36450-114">例如，如果你的应用程序具有打开的任何窗体，您应关闭它们再控制达到`End`语句。</span><span class="sxs-lookup"><span data-stu-id="36450-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="36450-115">应使用`End`尽量少，且仅当需要立即停止。</span><span class="sxs-lookup"><span data-stu-id="36450-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="36450-116">终止一个过程的正常方法 ([Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)并[退出语句](../../../visual-basic/language-reference/statements/exit-statement.md)) 不仅彻底关闭该过程，但也使调用代码有机会彻底关闭。</span><span class="sxs-lookup"><span data-stu-id="36450-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="36450-117">控制台应用程序，例如，可以只需`Return`从`Main`过程。</span><span class="sxs-lookup"><span data-stu-id="36450-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="36450-118">`End`语句也会调用<xref:System.Environment.Exit%2A>方法<xref:System.Environment>类中<xref:System>命名空间。</span><span class="sxs-lookup"><span data-stu-id="36450-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="36450-119"><xref:System.Environment.Exit%2A> 要求具有`UnmanagedCode`权限。</span><span class="sxs-lookup"><span data-stu-id="36450-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="36450-120">如果没有，<xref:System.Security.SecurityException>发生错误。</span><span class="sxs-lookup"><span data-stu-id="36450-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="36450-121">当其他关键字后, 跟[最终\<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)描述相应的过程或块定义的末尾。</span><span class="sxs-lookup"><span data-stu-id="36450-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="36450-122">例如，`End Function`终止的定义`Function`过程。</span><span class="sxs-lookup"><span data-stu-id="36450-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36450-123">示例</span><span class="sxs-lookup"><span data-stu-id="36450-123">Example</span></span>  
 <span data-ttu-id="36450-124">下面的示例使用`End`语句终止执行代码，如果用户请求它。</span><span class="sxs-lookup"><span data-stu-id="36450-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="36450-125">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="36450-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="36450-126">不支持此语句。</span><span class="sxs-lookup"><span data-stu-id="36450-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36450-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="36450-127">See also</span></span>
- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="36450-128">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="36450-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="36450-129">结束\<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="36450-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
