---
title: "如何：将事件信息写入文本文件 (Visual Basic)"
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
- event logs [Visual Studio], writing event information
- text files, writing event information to a text file
- events [Visual Basic], writing event information to a text file
ms.assetid: 9ca7cc03-bf99-4933-9e5e-61ee28e9a6b4
caps.latest.revision: 20
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
ms.openlocfilehash: a8008f25198928e0bf2bd7e1c0caee8118b8fec9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-event-information-to-a-text-file-visual-basic"></a><span data-ttu-id="fed4d-102">如何：将事件信息写入文本文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fed4d-102">How to: Write Event Information to a Text File (Visual Basic)</span></span>
<span data-ttu-id="fed4d-103">可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序中所发生事件的信息。</span><span class="sxs-lookup"><span data-stu-id="fed4d-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span> <span data-ttu-id="fed4d-104">本示例演示如何使用 `My.Application.Log.WriteEntry` 方法将跟踪信息记录到日志文件中。</span><span class="sxs-lookup"><span data-stu-id="fed4d-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information to a log file.</span></span>  
  
### <a name="to-add-and-configure-the-file-log-listener"></a><span data-ttu-id="fed4d-105">添加和配置文件日志侦听器</span><span class="sxs-lookup"><span data-stu-id="fed4d-105">To add and configure the file log listener</span></span>  
  
1.  <span data-ttu-id="fed4d-106">在“解决方案资源管理器” 中右键单击 app.config，然后选择“打开”。</span><span class="sxs-lookup"><span data-stu-id="fed4d-106">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="fed4d-107">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="fed4d-107">\- or -</span></span>  
  
     <span data-ttu-id="fed4d-108">如果其中没有 app.config 文件：</span><span class="sxs-lookup"><span data-stu-id="fed4d-108">If there is no app.config file:</span></span>  
  
    1.  <span data-ttu-id="fed4d-109">在 **“项目”** 菜单上选择 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="fed4d-109">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="fed4d-110">在“添加新项”  对话框中，选择“应用程序配置文件” 。</span><span class="sxs-lookup"><span data-stu-id="fed4d-110">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="fed4d-111">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="fed4d-111">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="fed4d-112">在应用程序配置文件中找到 `<listeners>` 部分。</span><span class="sxs-lookup"><span data-stu-id="fed4d-112">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="fed4d-113">\<侦听器> 部分位于 name 属性为“DefaultSource”的 \<源> 部分中，后者嵌套在 \<system.diagnostics> 部分中，该部分又嵌套在顶级 \<配置> 部分下。</span><span class="sxs-lookup"><span data-stu-id="fed4d-113">You will find the \<listeners> section in the \<source> section with the name attribute "DefaultSource", which is nested under the \<system.diagnostics> section, which is nested under the top-level \<configuration> section.</span></span>  
  
3.  <span data-ttu-id="fed4d-114">将此元素添加到该 `<listeners>` 部分：</span><span class="sxs-lookup"><span data-stu-id="fed4d-114">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener" />  
    ```  
  
4.  <span data-ttu-id="fed4d-115">找到 `<sharedListeners>` 部分，该部分位于 `<system.diagnostics>` 部分中，后者嵌套在顶级 `<configuration>` 部分之下。</span><span class="sxs-lookup"><span data-stu-id="fed4d-115">Locate the `<sharedListeners>` section in the `<system.diagnostics>` section, nested under the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="fed4d-116">将此元素添加到该 `<sharedListeners>` 部分：</span><span class="sxs-lookup"><span data-stu-id="fed4d-116">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="FileLogListener"   
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,   
              Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
              PublicKeyToken=b03f5f7f11d50a3a"  
        initializeData="FileLogListenerWriter"  
        location="Custom"  
        customlocation="c:\temp\" />  
    ```  
  
     <span data-ttu-id="fed4d-117">将 `customlocation` 属性的值更改为日志目录。</span><span class="sxs-lookup"><span data-stu-id="fed4d-117">Change the value of the `customlocation` attribute to the log directory.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fed4d-118">若要设置侦听器属性的值，请使用与该属性具有相同名称的特性，名称中的所有字母都为小写。</span><span class="sxs-lookup"><span data-stu-id="fed4d-118">To set the value of a listener property, use an attribute that has the same name as the property, with all letters in the name lowercase.</span></span> <span data-ttu-id="fed4d-119">例如，`location` 和 `customlocation` 属性设置 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> 和 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="fed4d-119">For example, the `location` and `customlocation` attributes set the values of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.Location%2A> and <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.CustomLocation%2A> properties.</span></span>  
  
### <a name="to-write-event-information-to-the-file-log"></a><span data-ttu-id="fed4d-120">将事件信息写入文件日志</span><span class="sxs-lookup"><span data-stu-id="fed4d-120">To write event information to the file log</span></span>  
  
-   <span data-ttu-id="fed4d-121">可以使用 `My.Application.Log.WriteEntry` 或 `My.Application.Log.WriteException` 方法将信息写入文件日志。</span><span class="sxs-lookup"><span data-stu-id="fed4d-121">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the file log.</span></span> <span data-ttu-id="fed4d-122">有关详细信息，请参阅[如何：编写日志消息](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)和[如何：记录异常](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fed4d-122">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="fed4d-123">为程序集配置文件日志侦听器后，它将接收该程序集写入 `My.Application.Log` 的所有消息。</span><span class="sxs-lookup"><span data-stu-id="fed4d-123">After you configure the file log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed4d-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fed4d-124">See Also</span></span>  
 <span data-ttu-id="fed4d-125"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="fed4d-125"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="fed4d-126"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span><span class="sxs-lookup"><span data-stu-id="fed4d-126"><xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A></span></span>   
 <span data-ttu-id="fed4d-127"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span><span class="sxs-lookup"><span data-stu-id="fed4d-127"><xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A></span></span>   
 <span data-ttu-id="fed4d-128">[使用应用程序日志](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="fed4d-128">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 [<span data-ttu-id="fed4d-129">如何：日志异常</span><span class="sxs-lookup"><span data-stu-id="fed4d-129">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)

