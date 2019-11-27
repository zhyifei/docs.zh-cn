---
title: End 语句
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
ms.openlocfilehash: cb2fb4abb21b7b9c6575cec4aca1374f63687607
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343720"
---
# <a name="end-statement"></a><span data-ttu-id="d6819-102">End 语句</span><span class="sxs-lookup"><span data-stu-id="d6819-102">End Statement</span></span>
<span data-ttu-id="d6819-103">立即终止执行。</span><span class="sxs-lookup"><span data-stu-id="d6819-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6819-104">语法</span><span class="sxs-lookup"><span data-stu-id="d6819-104">Syntax</span></span>  
  
```vb  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="d6819-105">备注</span><span class="sxs-lookup"><span data-stu-id="d6819-105">Remarks</span></span>  
 <span data-ttu-id="d6819-106">可以将 `End` 语句放置在过程中的任意位置，以强制整个应用程序停止运行。</span><span class="sxs-lookup"><span data-stu-id="d6819-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="d6819-107">`End` 关闭使用 `Open` 语句打开的所有文件，并清除应用程序的所有变量。</span><span class="sxs-lookup"><span data-stu-id="d6819-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="d6819-108">应用程序将立即关闭，因为没有任何其他程序保留对其对象的引用，并且没有任何代码正在运行。</span><span class="sxs-lookup"><span data-stu-id="d6819-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d6819-109">`End` 语句会突然停止代码执行，并且不会调用 `Dispose` 或 `Finalize` 方法或其他任何 Visual Basic 代码。</span><span class="sxs-lookup"><span data-stu-id="d6819-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="d6819-110">其他程序持有的对象引用已失效。</span><span class="sxs-lookup"><span data-stu-id="d6819-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="d6819-111">如果在 `Try` 或 `Catch` 块内遇到 `End` 语句，控件不会传递给相应的 `Finally` 块。</span><span class="sxs-lookup"><span data-stu-id="d6819-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="d6819-112">`Stop` 语句会挂起执行，但与 `End`不同，它不会关闭任何文件或清除任何变量，除非在已编译的可执行（.exe）文件中遇到该错误。</span><span class="sxs-lookup"><span data-stu-id="d6819-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="d6819-113">由于 `End` 终止应用程序而不参与任何可能已打开的资源，因此，在使用之前，应尝试完全关闭。</span><span class="sxs-lookup"><span data-stu-id="d6819-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="d6819-114">例如，如果您的应用程序打开了任何窗体，则在控制到达 `End` 语句之前应关闭它们。</span><span class="sxs-lookup"><span data-stu-id="d6819-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="d6819-115">应慎用 `End`，且仅在需要立即停止时使用。</span><span class="sxs-lookup"><span data-stu-id="d6819-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="d6819-116">终止过程的一般方法（[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)和[Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)）不仅完全关闭过程，而且还使调用代码有机会彻底关闭。</span><span class="sxs-lookup"><span data-stu-id="d6819-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="d6819-117">例如，控制台应用程序可以从 `Main` 过程中简单地 `Return`。</span><span class="sxs-lookup"><span data-stu-id="d6819-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d6819-118">`End` 语句调用 <xref:System> 命名空间中 <xref:System.Environment> 类的 <xref:System.Environment.Exit%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d6819-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="d6819-119"><xref:System.Environment.Exit%2A> 要求您具有 `UnmanagedCode` 权限。</span><span class="sxs-lookup"><span data-stu-id="d6819-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="d6819-120">否则，会发生 <xref:System.Security.SecurityException> 错误。</span><span class="sxs-lookup"><span data-stu-id="d6819-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="d6819-121">后跟一个附加关键字时， [end \<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)指定相应过程或块定义的末尾。</span><span class="sxs-lookup"><span data-stu-id="d6819-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="d6819-122">例如，`End Function` 终止 `Function` 过程的定义。</span><span class="sxs-lookup"><span data-stu-id="d6819-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6819-123">示例</span><span class="sxs-lookup"><span data-stu-id="d6819-123">Example</span></span>  
 <span data-ttu-id="d6819-124">下面的示例使用 `End` 语句在用户请求代码的情况下终止代码执行。</span><span class="sxs-lookup"><span data-stu-id="d6819-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="d6819-125">智能设备开发人员说明</span><span class="sxs-lookup"><span data-stu-id="d6819-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="d6819-126">不支持此语句。</span><span class="sxs-lookup"><span data-stu-id="d6819-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6819-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6819-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="d6819-128">Stop 语句</span><span class="sxs-lookup"><span data-stu-id="d6819-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="d6819-129">End \<关键字 > 语句</span><span class="sxs-lookup"><span data-stu-id="d6819-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
