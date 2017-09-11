---
title: "如何：当应用程序启动或关闭时记录消息 (Visual Basic)"
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
- event logs, shutdown
- My.Application.Log object, logging
- Startup event
- event logs, startup
- Shutdown event
- My.Log object, logging
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fa5bf57ac5245e9363089b85607b7e6d1a00ba14
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-log-messages-when-the-application-starts-or-shuts-down-visual-basic"></a><span data-ttu-id="c06a8-102">如何：当应用程序启动或关闭时记录消息 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c06a8-102">How to: Log Messages When the Application Starts or Shuts Down (Visual Basic)</span></span>
<span data-ttu-id="c06a8-103">可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序中所发生事件的信息。</span><span class="sxs-lookup"><span data-stu-id="c06a8-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="c06a8-104">本示例将演示如何结合使用 `My.Application.Log.WriteEntry` 方法与 `Startup` 和 `Shutdown` 事件来写入跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="c06a8-104">This example shows how to use the `My.Application.Log.WriteEntry` method with the `Startup` and `Shutdown` events to write tracing information.</span></span>  
  
### <a name="to-access-the-applications-event-handler-code"></a><span data-ttu-id="c06a8-105">访问应用程序的事件处理程序代码</span><span class="sxs-lookup"><span data-stu-id="c06a8-105">To access the application's event-handler code</span></span>  
  
1.  <span data-ttu-id="c06a8-106">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="c06a8-106">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c06a8-107">在 **“项目”** 菜单上，选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="c06a8-107">On the **Project** menu, choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="c06a8-108">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="c06a8-108">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="c06a8-109">单击“查看应用程序事件”  按钮，打开“代码编辑器”。</span><span class="sxs-lookup"><span data-stu-id="c06a8-109">Click the **View Application Events** button to open the Code Editor.</span></span>  
  
     <span data-ttu-id="c06a8-110">此时将打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-110">This opens the ApplicationEvents.vb file.</span></span>  
  
### <a name="to-log-messages-when-the-application-starts"></a><span data-ttu-id="c06a8-111">在应用程序启动时记录消息</span><span class="sxs-lookup"><span data-stu-id="c06a8-111">To log messages when the application starts</span></span>  
  
1.  <span data-ttu-id="c06a8-112">在“代码编辑器”中打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-112">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="c06a8-113">在“常规”  菜单上，选择“MyApplication 事件” 。</span><span class="sxs-lookup"><span data-stu-id="c06a8-113">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="c06a8-114">在“声明”  菜单上，选择“启动” 。</span><span class="sxs-lookup"><span data-stu-id="c06a8-114">On the **Declarations** menu, choose **Startup**.</span></span>  
  
     <span data-ttu-id="c06a8-115">在主应用程序运行之前，应用程序将引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 事件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-115">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> event before the main application runs.</span></span>  
  
3.  <span data-ttu-id="c06a8-116">将 `My.Application.Log.WriteEntry` 方法添加到 `Startup` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c06a8-116">Add the `My.Application.Log.WriteEntry` method to the `Startup` event handler.</span></span>  
  
     <span data-ttu-id="c06a8-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c06a8-117">[!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]</span></span>  
  
### <a name="to-log-messages-when-the-application-shuts-down"></a><span data-ttu-id="c06a8-118">在应用程序关闭时记录消息</span><span class="sxs-lookup"><span data-stu-id="c06a8-118">To log messages when the application shuts down</span></span>  
  
1.  <span data-ttu-id="c06a8-119">在“代码编辑器”中打开 ApplicationEvents.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-119">Have the ApplicationEvents.vb file open in the Code Editor.</span></span> <span data-ttu-id="c06a8-120">在“常规”  菜单上，选择“MyApplication 事件” 。</span><span class="sxs-lookup"><span data-stu-id="c06a8-120">On the **General** menu, choose **MyApplication Events**.</span></span>  
  
2.  <span data-ttu-id="c06a8-121">在“声明”  菜单上，选择“关闭” 。</span><span class="sxs-lookup"><span data-stu-id="c06a8-121">On the **Declarations** menu, choose **Shutdown**.</span></span>  
  
     <span data-ttu-id="c06a8-122">在主应用程序运行之后、关闭之前，应用程序将引发 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 事件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-122">The application raises the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> event after the main application runs, but before it shuts down.</span></span>  
  
3.  <span data-ttu-id="c06a8-123">将 `My.Application.Log.WriteEntry` 方法添加到 `Shutdown` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c06a8-123">Add the `My.Application.Log.WriteEntry` method to the `Shutdown` event handler.</span></span>  
  
     <span data-ttu-id="c06a8-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c06a8-124">[!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="c06a8-125">示例</span><span class="sxs-lookup"><span data-stu-id="c06a8-125">Example</span></span>  
 <span data-ttu-id="c06a8-126">可以通过“项目设计器” 访问“代码编辑器”中的应用程序事件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-126">You can use the **Project Designer** to access the application events in the Code Editor.</span></span> <span data-ttu-id="c06a8-127">有关详细信息，请参阅 [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic)（应用程序页、项目设计器 (Visual Basic)。</span><span class="sxs-lookup"><span data-stu-id="c06a8-127">For more information, see [Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="c06a8-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c06a8-128">[!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06a8-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c06a8-129">See Also</span></span>  
 <span data-ttu-id="c06a8-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c06a8-130"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="c06a8-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="c06a8-131"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="c06a8-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="c06a8-132"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="c06a8-133">[应用程序页、项目设计器 (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="c06a8-133">[Application Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic) </span></span>  
 [<span data-ttu-id="c06a8-134">使用应用程序日志</span><span class="sxs-lookup"><span data-stu-id="c06a8-134">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)

