---
title: 如何：在 Visual Basic 中记录异常
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, logging
- exceptions, tracking
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
ms.openlocfilehash: 53bf93a326123ddb1e26ef5964fa057148505116
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307218"
---
# <a name="how-to-log-exceptions-in-visual-basic"></a><span data-ttu-id="a16d1-102">如何：在 Visual Basic 中记录异常</span><span class="sxs-lookup"><span data-stu-id="a16d1-102">How to: Log Exceptions in Visual Basic</span></span>
<span data-ttu-id="a16d1-103">可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序中所发生异常的信息。</span><span class="sxs-lookup"><span data-stu-id="a16d1-103">You can use the `My.Application.Log` and `My.Log` objects to log information about exceptions that occur in your application.</span></span> <span data-ttu-id="a16d1-104">这些示例演示如何使用 `My.Application.Log.WriteException` 方法来记录显式捕获的异常和未处理的异常。</span><span class="sxs-lookup"><span data-stu-id="a16d1-104">These examples show how to use the `My.Application.Log.WriteException` method to log exceptions that you catch explicitly and exceptions that are unhandled.</span></span>  
  
 <span data-ttu-id="a16d1-105">若要记录跟踪信息，请使用 `My.Application.Log.WriteEntry` 方法。</span><span class="sxs-lookup"><span data-stu-id="a16d1-105">For logging tracing information, use the `My.Application.Log.WriteEntry` method.</span></span> <span data-ttu-id="a16d1-106">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>。</span><span class="sxs-lookup"><span data-stu-id="a16d1-106">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>  
  
### <a name="to-log-a-handled-exception"></a><span data-ttu-id="a16d1-107">记录已处理的异常</span><span class="sxs-lookup"><span data-stu-id="a16d1-107">To log a handled exception</span></span>  
  
1. <span data-ttu-id="a16d1-108">创建将生成异常信息的方法。</span><span class="sxs-lookup"><span data-stu-id="a16d1-108">Create the method that will generate the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#9)]  
  
2. <span data-ttu-id="a16d1-109">使用 `Try...Catch` 块捕获该异常。</span><span class="sxs-lookup"><span data-stu-id="a16d1-109">Use a `Try...Catch` block to catch the exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#6)]  
  
3. <span data-ttu-id="a16d1-110">将可能生成异常的代码置于 `Try` 块中。</span><span class="sxs-lookup"><span data-stu-id="a16d1-110">Put the code that could generate an exception in the `Try` block.</span></span>  
  
     <span data-ttu-id="a16d1-111">取消注释 `Dim` 和 `MsgBox` 行，导致 <xref:System.NullReferenceException> 异常。</span><span class="sxs-lookup"><span data-stu-id="a16d1-111">Uncomment the `Dim` and `MsgBox` lines to cause a <xref:System.NullReferenceException> exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#7)]  
  
4. <span data-ttu-id="a16d1-112">在 `Catch` 块中，使用 `My.Application.Log.WriteException` 方法写入异常信息。</span><span class="sxs-lookup"><span data-stu-id="a16d1-112">In the `Catch` block, use the `My.Application.Log.WriteException` method to write the exception information.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#8)]  
  
     <span data-ttu-id="a16d1-113">下面的示例演示用于记录已处理的异常的完整代码。</span><span class="sxs-lookup"><span data-stu-id="a16d1-113">The following example shows the complete code for logging a handled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#10)]  
  
### <a name="to-log-an-unhandled-exception"></a><span data-ttu-id="a16d1-114">记录未处理的异常</span><span class="sxs-lookup"><span data-stu-id="a16d1-114">To log an unhandled exception</span></span>  
  
1. <span data-ttu-id="a16d1-115">在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="a16d1-115">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a16d1-116">在 **“项目”** 菜单上，选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="a16d1-116">On the **Project** menu, choose **Properties**.</span></span>  
  
2. <span data-ttu-id="a16d1-117">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="a16d1-117">Click the **Application** tab.</span></span>  
  
3. <span data-ttu-id="a16d1-118">单击“查看应用程序事件”  按钮，打开“代码编辑器”。</span><span class="sxs-lookup"><span data-stu-id="a16d1-118">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="a16d1-119">此时将打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="a16d1-119">This opens the ApplicationEvents.vb file.</span></span>  
  
4. <span data-ttu-id="a16d1-120">在“代码编辑器”中打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="a16d1-120">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="a16d1-121">在“常规”  菜单上，选择“MyApplication 事件”。</span><span class="sxs-lookup"><span data-stu-id="a16d1-121">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
5. <span data-ttu-id="a16d1-122">在“声明”菜单上，选择“UnhandledException”。</span><span class="sxs-lookup"><span data-stu-id="a16d1-122">On the **Declarations** menu, choose **UnhandledException**.</span></span>  
  
     <span data-ttu-id="a16d1-123">在主应用程序运行之前，应用程序将引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 事件。</span><span class="sxs-lookup"><span data-stu-id="a16d1-123">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> event before the main application runs.</span></span>  
  
6. <span data-ttu-id="a16d1-124">将 `My.Application.Log.WriteException` 方法添加到 `UnhandledException` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a16d1-124">Add the `My.Application.Log.WriteException` method to the `UnhandledException` event handler.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#4)]  
  
     <span data-ttu-id="a16d1-125">下面的示例演示用于记录未处理的异常的完整代码。</span><span class="sxs-lookup"><span data-stu-id="a16d1-125">The following example shows the complete code for logging an unhandled exception.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/MyEventsFake.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a16d1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a16d1-126">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="a16d1-127">使用应用程序日志</span><span class="sxs-lookup"><span data-stu-id="a16d1-127">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="a16d1-128">如何：写入日志消息</span><span class="sxs-lookup"><span data-stu-id="a16d1-128">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="a16d1-129">演练：确定 My.Application.Log 在哪里写入信息</span><span class="sxs-lookup"><span data-stu-id="a16d1-129">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="a16d1-130">演练：更改 My.Application.Log 在哪里写入信息</span><span class="sxs-lookup"><span data-stu-id="a16d1-130">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
