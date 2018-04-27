---
title: 如何：将 Web 浏览器功能添加到 Windows 窗体应用程序
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3e7cde23c7395e778f8f6cf9b13f998dded18d69
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="d3211-102">如何：将 Web 浏览器功能添加到 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="d3211-102">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>
<span data-ttu-id="d3211-103">使用 <xref:System.Windows.Forms.WebBrowser> 控件，可将 Web 浏览器功能添加到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d3211-103">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="d3211-104">默认情况下，该控件的工作方式类似于 Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="d3211-104">The control works like a Web browser by default.</span></span> <span data-ttu-id="d3211-105">通过设置 <xref:System.Windows.Forms.WebBrowser.Url%2A> 属性加载初始 URL 后，可以通过单击超链接或通过使用键盘快捷方式在导航历史记录中后移或前移，从而进行导航。</span><span class="sxs-lookup"><span data-stu-id="d3211-105">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="d3211-106">默认情况下，可以通过右键单击快捷菜单来访问其他浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="d3211-106">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="d3211-107">还可通过将新文档置于控件上来打开它们。</span><span class="sxs-lookup"><span data-stu-id="d3211-107">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="d3211-108"><xref:System.Windows.Forms.WebBrowser> 控件还具有几个属性、方法和事件，可将它们可用于实现与 Internet Explorer 中类似的用户界面功能。</span><span class="sxs-lookup"><span data-stu-id="d3211-108">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>  
  
 <span data-ttu-id="d3211-109">下面的代码示例实现地址栏、典型的浏览器按钮、“文件”菜单、状态栏以及显示当前页标题的标题栏。</span><span class="sxs-lookup"><span data-stu-id="d3211-109">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3211-110">示例</span><span class="sxs-lookup"><span data-stu-id="d3211-110">Example</span></span>  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d3211-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="d3211-111">Compiling the Code</span></span>  
 <span data-ttu-id="d3211-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d3211-112">This example requires:</span></span>  
  
-   <span data-ttu-id="d3211-113">对 `System,``System.Drawing` 和 `System.Windows.Forms` 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d3211-113">References to the `System,``System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>  
  
 <span data-ttu-id="d3211-114">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="d3211-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="d3211-115">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="d3211-115">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="d3211-116">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="d3211-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3211-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3211-117">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="d3211-118">WebBrowser 控件</span><span class="sxs-lookup"><span data-stu-id="d3211-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)
