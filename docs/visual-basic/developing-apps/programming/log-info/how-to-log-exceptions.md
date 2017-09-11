---
title: "如何：在 Visual Basic 中记录异常"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: adf2dc683a139d21f24379efc779d4510a2057eb
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="45bc2-102">如何：在 Visual Basic 中记录异常</span><span class="sxs-lookup"><span data-stu-id="45bc2-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="45bc2-103">可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序中所发生异常的信息。</span><span class="sxs-lookup"><span data-stu-id="45bc2-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="45bc2-104">这些示例演示如何使用 `My.Application.Log.WriteException` 方法来记录显式捕获的异常和未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="45bc2-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="45bc2-105">若要记录跟踪信息，请使用 `My.Application.Log.WriteEntry` 方法。</span><span class="sxs-lookup"><span data-stu-id="45bc2-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="45bc2-106">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>。</span><span class="sxs-lookup"><span data-stu-id="45bc2-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="45bc2-107">记录已处理的异常</span><span class="sxs-lookup"><span data-stu-id="45bc2-107">To log a handled exception</span></span>  
  
1.  <span data-ttu-id="45bc2-108">创建将生成异常信息的方法。</span><span class="sxs-lookup"><span data-stu-id="45bc2-108">Create the method that will generate the exception information.</span></span>  
  
     <span data-ttu-id="45bc2-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-109">[!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]</span></span>  
  
2.  <span data-ttu-id="45bc2-110">使用 `Try...Catch` 块捕获该异常。</span><span class="sxs-lookup"><span data-stu-id="45bc2-110">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     <span data-ttu-id="45bc2-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-111">[!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]</span></span>  
  
3.  <span data-ttu-id="45bc2-112">将可能生成异常的代码置于 `Try` 块中。</span><span class="sxs-lookup"><span data-stu-id="45bc2-112">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="45bc2-113">取消注释 `Dim` 和 `MsgBox` 行，导致 <xref:System.NullReferenceException> 异常。</span><span class="sxs-lookup"><span data-stu-id="45bc2-113">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     <span data-ttu-id="45bc2-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-114">[!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]</span></span>  
  
4.  <span data-ttu-id="45bc2-115">在 `Catch` 块中，使用 `My.Application.Log.WriteException` 方法写入异常信息。</span><span class="sxs-lookup"><span data-stu-id="45bc2-115">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     <span data-ttu-id="45bc2-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-116">[!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]</span></span>  
  
     <span data-ttu-id="45bc2-117">下面的示例演示用于记录已处理的异常的完整代码。</span><span class="sxs-lookup"><span data-stu-id="45bc2-117">The following example shows the complete code for logging a handled exception.</span></span>  
  
     <span data-ttu-id="45bc2-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-118">[!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]</span></span>  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="45bc2-119">记录未处理的异常</span><span class="sxs-lookup"><span data-stu-id="45bc2-119">To log an unhandled exception</span></span>  
  
1.  <span data-ttu-id="45bc2-120">在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="45bc2-120">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="45bc2-121">在 **“项目”** 菜单上，选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="45bc2-121">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="45bc2-122">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="45bc2-122">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="45bc2-123">单击“查看应用程序事件”  按钮，打开“代码编辑器”。</span><span class="sxs-lookup"><span data-stu-id="45bc2-123">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="45bc2-124">此时将打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="45bc2-124">This opens the ApplicationEvents.vb file.</span></span>  
  
4.  <span data-ttu-id="45bc2-125">在“代码编辑器”中打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="45bc2-125">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="45bc2-126">在“常规”  菜单上，选择“MyApplication 事件”。</span><span class="sxs-lookup"><span data-stu-id="45bc2-126">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5.  <span data-ttu-id="45bc2-127">在“声明”菜单上，选择“UnhandledException”。</span><span class="sxs-lookup"><span data-stu-id="45bc2-127">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="45bc2-128">在主应用程序运行之前，应用程序将引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 事件。</span><span class="sxs-lookup"><span data-stu-id="45bc2-128">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6.  <span data-ttu-id="45bc2-129">将 `My.Application.Log.WriteException` 方法添加到 `UnhandledException` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="45bc2-129">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     <span data-ttu-id="45bc2-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-130">[!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]</span></span>  
  
     <span data-ttu-id="45bc2-131">下面的示例演示用于记录未处理的异常的完整代码。</span><span class="sxs-lookup"><span data-stu-id="45bc2-131">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     <span data-ttu-id="45bc2-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="45bc2-132">[!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45bc2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45bc2-133">See Also</span></span>  
 <span data-ttu-id="45bc2-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="45bc2-134"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="45bc2-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="45bc2-135"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="45bc2-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="45bc2-136"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="45bc2-137">[使用应用程序日志](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="45bc2-137">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="45bc2-138">[如何：编写日志消息](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="45bc2-138">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="45bc2-139">[演练：确定 My.Application.Log 写入信息的位置](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="45bc2-139">[Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md) </span></span>  
 [<span data-ttu-id="45bc2-140">演练：更改 My.Application.Log 写入信息的位置</span><span class="sxs-lookup"><span data-stu-id="45bc2-140">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)

