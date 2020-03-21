---
title: 对话框概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187454"
---
# <a name="dialog-boxes-overview"></a><span data-ttu-id="fb226-102">对话框概述</span><span class="sxs-lookup"><span data-stu-id="fb226-102">Dialog boxes overview</span></span>
<span data-ttu-id="fb226-103">独立应用程序通常有一个主窗口，该窗口既显示应用程序运行的主数据，又公开通过[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]菜单栏、工具栏和状态栏等机制处理该数据的功能。</span><span class="sxs-lookup"><span data-stu-id="fb226-103">Standalone applications typically have a main window that both displays the main data over which the application operates and exposes the functionality to process that data through [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mechanisms like menu bars, tool bars, and status bars.</span></span> <span data-ttu-id="fb226-104">重要的应用程序可能还会显示其他窗口来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fb226-104">A non-trivial application may also display additional windows to do the following:</span></span>  
  
- <span data-ttu-id="fb226-105">向用户显示特定信息。</span><span class="sxs-lookup"><span data-stu-id="fb226-105">Display specific information to users.</span></span>  
  
- <span data-ttu-id="fb226-106">从用户处收集信息。</span><span class="sxs-lookup"><span data-stu-id="fb226-106">Gather information from users.</span></span>  
  
- <span data-ttu-id="fb226-107">同时显示并收集信息。</span><span class="sxs-lookup"><span data-stu-id="fb226-107">Both display and gather information.</span></span>  
  
 <span data-ttu-id="fb226-108">这些类型的窗口称为*对话框*，有两种类型：模式和无模式。</span><span class="sxs-lookup"><span data-stu-id="fb226-108">These types of windows are known as *dialog boxes*, and there are two types: modal and modeless.</span></span>  
  
 <span data-ttu-id="fb226-109">当函数需要用户的其他数据以继续时，函数将显示*模式*对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-109">A *modal* dialog box is displayed by a function when the function needs additional data from a user to continue.</span></span> <span data-ttu-id="fb226-110">由于函数依赖于模式对话框收集数据，模式对话框还会在其保持打开状态时防止用户激活应用程序中的其他窗口。</span><span class="sxs-lookup"><span data-stu-id="fb226-110">Because the function depends on the modal dialog box to gather data, the modal dialog box also prevents a user from activating other windows in the application while it remains open.</span></span> <span data-ttu-id="fb226-111">在大多数情况下，模式对话框允许用户在完成模式对话框后通过按下 **"确定"** 或 **"取消"** 按钮发出信号。</span><span class="sxs-lookup"><span data-stu-id="fb226-111">In most cases, a modal dialog box allows a user to signal when they have finished with the modal dialog box by pressing either an **OK** or **Cancel** button.</span></span> <span data-ttu-id="fb226-112">按下 **"确定"** 按钮表示用户已输入数据，并希望该函数继续处理该数据。</span><span class="sxs-lookup"><span data-stu-id="fb226-112">Pressing the **OK** button indicates that a user has entered data and wants the function to continue processing with that data.</span></span> <span data-ttu-id="fb226-113">按下 **"取消"** 按钮表示用户希望完全停止该函数的执行。</span><span class="sxs-lookup"><span data-stu-id="fb226-113">Pressing the **Cancel** button indicates that a user wants to stop the function from executing altogether.</span></span> <span data-ttu-id="fb226-114">最常见的模式对话框示例显示为可以打开、保存并打印数据。</span><span class="sxs-lookup"><span data-stu-id="fb226-114">The most common examples of modal dialog boxes are shown to open, save, and print data.</span></span>  
  
 <span data-ttu-id="fb226-115">另一方面，*无模式*对话框不会阻止用户在打开时激活其他窗口。</span><span class="sxs-lookup"><span data-stu-id="fb226-115">A *modeless* dialog box, on the other hand, does not prevent a user from activating other windows while it is open.</span></span> <span data-ttu-id="fb226-116">例如，如果用户想要在某个文档中查找特定字的出现次数，主窗口通常会打开一个对话框，询问用户要查找的字是什么。</span><span class="sxs-lookup"><span data-stu-id="fb226-116">For example, if a user wants to find occurrences of a particular word in a document, a main window will often open a dialog box to ask a user what word they are looking for.</span></span> <span data-ttu-id="fb226-117">查找字并不会防止用户编辑文档，因此对话框无需为模式对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-117">Since finding a word doesn't prevent a user from editing the document, however, the dialog box doesn't need to be modal.</span></span> <span data-ttu-id="fb226-118">无模式对话框至少提供关闭对话框的 **"关闭"** 按钮，并可能提供用于执行特定功能的其他按钮，例如 **"查找下一步**"按钮，以查找与单词搜索的查找条件匹配的下一个单词。</span><span class="sxs-lookup"><span data-stu-id="fb226-118">A modeless dialog box at least provides a **Close** button to close the dialog box, and may provide additional buttons to execute specific functions, such as a **Find Next** button to find the next word that matches the find criteria of a word search.</span></span>  
  
 <span data-ttu-id="fb226-119">Windows 演示文稿基础 （WPF） 允许您创建多种类型的对话框，包括消息框、通用对话框和自定义对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-119">Windows Presentation Foundation (WPF) allows you to create several types of dialog boxes, including message boxes, common dialog boxes, and custom dialog boxes.</span></span> <span data-ttu-id="fb226-120">本主题讨论每个，[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)提供匹配的示例。</span><span class="sxs-lookup"><span data-stu-id="fb226-120">This topic discusses each, and the [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) provides matching examples.</span></span>  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a><span data-ttu-id="fb226-121">消息框</span><span class="sxs-lookup"><span data-stu-id="fb226-121">Message boxes</span></span>  
 <span data-ttu-id="fb226-122">*消息框*是一个对话框，可用于显示文本信息并允许用户使用按钮做出决定。</span><span class="sxs-lookup"><span data-stu-id="fb226-122">A *message box* is a dialog box that can be used to display textual information and to allow users to make decisions with buttons.</span></span> <span data-ttu-id="fb226-123">下图显示的消息框显示文本信息、提出问题并向用户提供了三个按钮来回答问题。</span><span class="sxs-lookup"><span data-stu-id="fb226-123">The following figure shows a message box that displays textual information, asks a question, and provides the user with three buttons to answer the question.</span></span>  
  
 ![Word 处理器对话框，询问是否要在应用程序关闭之前保存对文档的更改。](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 <span data-ttu-id="fb226-125">要创建消息框，请使用 类<xref:System.Windows.MessageBox>。</span><span class="sxs-lookup"><span data-stu-id="fb226-125">To create a message box, you use the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="fb226-126"><xref:System.Windows.MessageBox>允许您使用如下所示的代码配置消息框文本、标题、图标和按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-126"><xref:System.Windows.MessageBox> lets you configure the message box text, title, icon, and buttons, using code like the following.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 <span data-ttu-id="fb226-127">要显示消息框，请调用`static`<xref:System.Windows.MessageBox.Show%2A>方法，如下代码所示。</span><span class="sxs-lookup"><span data-stu-id="fb226-127">To show a message box, you call the `static`<xref:System.Windows.MessageBox.Show%2A> method, as demonstrated in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 <span data-ttu-id="fb226-128">当显示消息框的代码需要检测并处理用户决定（按下了哪个按钮）时，该代码可以检查消息框的结果，如以下代码中所示。</span><span class="sxs-lookup"><span data-stu-id="fb226-128">When code that shows a message box needs to detect and process the user's decision (which button was pressed), the code can inspect the message box result, as shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 <span data-ttu-id="fb226-129">有关使用消息框的详细信息，请参阅<xref:System.Windows.MessageBox>、[消息框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)和[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)。</span><span class="sxs-lookup"><span data-stu-id="fb226-129">For more information on using message boxes, see <xref:System.Windows.MessageBox>, [MessageBox Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox), and [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).</span></span>  
  
 <span data-ttu-id="fb226-130">尽管<xref:System.Windows.MessageBox>可以提供简单的对话框用户体验，但使用<xref:System.Windows.MessageBox>的优点是，在部分信任安全沙盒中运行的应用程序可以显示的唯一窗口类型（请参阅[安全性](../security-wpf.md)），如 XAML 浏览器应用程序 （XBAPs）。</span><span class="sxs-lookup"><span data-stu-id="fb226-130">Although <xref:System.Windows.MessageBox> may offer a simple dialog box user experience, the advantage of using <xref:System.Windows.MessageBox> is that is the only type of window that can be shown by applications that run within a partial trust security sandbox (see [Security](../security-wpf.md)), such as XAML browser applications (XBAPs).</span></span>  
  
 <span data-ttu-id="fb226-131">大多数对话框显示和收集比消息框结果更复杂的数据，包括文本、选项（复选框）、互斥选项（单选按钮）和列表选项（列表框、组合框、下拉列表框）。</span><span class="sxs-lookup"><span data-stu-id="fb226-131">Most dialog boxes display and gather more complex data than the result of a message box, including text, selection (check boxes), mutually exclusive selection (radio buttons), and list selection (list boxes, combo boxes, drop-down list boxes).</span></span> <span data-ttu-id="fb226-132">对于这些，Windows 演示文稿基础 （WPF） 提供了几个常见的对话框，并允许您创建自己的对话框，尽管其中任一对话框的使用仅限于完全信任运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb226-132">For these, Windows Presentation Foundation (WPF) provides several common dialog boxes and allows you to create your own dialog boxes, although the use of either is limited to applications running with full trust.</span></span>  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a><span data-ttu-id="fb226-133">常见对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-133">Common dialog boxes</span></span>  
 <span data-ttu-id="fb226-134">Windows 实现所有应用程序共有的各种可重用对话框，包括用于打开文件、保存文件和打印的对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-134">Windows implements a variety of reusable dialog boxes that are common to all applications, including dialog boxes for opening files, saving files, and printing.</span></span> <span data-ttu-id="fb226-135">这些对话框由操作系统实现，因此可以在运行于该操作系统上的所有应用程序之间共享，这对用户体验的一致性很有帮助；当用户熟悉一个应用程序中操作系统所提供的对话框时，他们就无需再去了解如何在其他应用程序中使用该对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-135">Since these dialog boxes are implemented by the operating system, they can be shared among all the applications that run on the operating system, which helps user experience consistency; when users are familiar with the use of an operating system-provided dialog box in one application, they don't need to learn how to use that dialog box in other applications.</span></span> <span data-ttu-id="fb226-136">由于这些对话框对所有应用程序都可用，并且因为它们有助于提供一致的用户体验，因此它们称为*通用对话框*。</span><span class="sxs-lookup"><span data-stu-id="fb226-136">Because these dialog boxes are available to all applications and because they help provide a consistent user experience, they are known as *common dialog boxes*.</span></span>  
  
 <span data-ttu-id="fb226-137">Windows 演示文稿基础 （WPF） 封装打开的文件、保存文件并打印公共对话框，并将其公开为托管类，供您在独立应用程序中使用。</span><span class="sxs-lookup"><span data-stu-id="fb226-137">Windows Presentation Foundation (WPF) encapsulates the open file, save file, and print common dialog boxes and exposes them as managed classes for you to use in standalone applications.</span></span> <span data-ttu-id="fb226-138">本主题提供每个通用对话框的简要概述。</span><span class="sxs-lookup"><span data-stu-id="fb226-138">This topic provides a brief overview of each.</span></span>  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a><span data-ttu-id="fb226-139">打开文件对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-139">Open File dialog</span></span>  
 <span data-ttu-id="fb226-140">如下图中所示的打开文件对话框由文件打开功能用于检索要打开文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fb226-140">The open file dialog box, shown in the following figure, is used by file opening functionality to retrieve the name of a file to open.</span></span>  
  
 ![显示要检索文件的位置的打开对话框。](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 <span data-ttu-id="fb226-142">公共打开的文件对话框作为类实现，<xref:Microsoft.Win32.OpenFileDialog>位于命名空间中。 <xref:Microsoft.Win32></span><span class="sxs-lookup"><span data-stu-id="fb226-142">The common open file dialog box is implemented as the <xref:Microsoft.Win32.OpenFileDialog> class and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="fb226-143">以下代码显示了如何创建、配置和显示打开文件对话框以及如何处理结果。</span><span class="sxs-lookup"><span data-stu-id="fb226-143">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 <span data-ttu-id="fb226-144">有关打开的文件对话框的详细信息，请参阅<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="fb226-144">For more information on the open file dialog box, see <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb226-145"><xref:Microsoft.Win32.OpenFileDialog>可用于通过运行具有部分信任的应用程序安全地检索文件名（请参阅[安全](../security-wpf.md)）。</span><span class="sxs-lookup"><span data-stu-id="fb226-145"><xref:Microsoft.Win32.OpenFileDialog> can be used to safely retrieve file names by applications running with partial trust (see [Security](../security-wpf.md)).</span></span>  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a><span data-ttu-id="fb226-146">保存文件对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-146">Save File dialog box</span></span>  
 <span data-ttu-id="fb226-147">如下图中所示的保存文件对话框由文件保存功能用以检索要保存的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fb226-147">The save file dialog box, shown in the following figure, is used by file saving functionality to retrieve the name of a file to save.</span></span>  
  
 ![显示保存文件的位置的对话框。](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 <span data-ttu-id="fb226-149">公共保存文件对话框作为<xref:Microsoft.Win32.SaveFileDialog>类实现，并位于命名空间中。 <xref:Microsoft.Win32></span><span class="sxs-lookup"><span data-stu-id="fb226-149">The common save file dialog box is implemented as the <xref:Microsoft.Win32.SaveFileDialog> class, and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="fb226-150">以下代码显示了如何创建、配置和显示打开文件对话框以及如何处理结果。</span><span class="sxs-lookup"><span data-stu-id="fb226-150">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 <span data-ttu-id="fb226-151">有关保存文件对话框的详细信息，请参阅<xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="fb226-151">For more information on the save file dialog box, see <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.</span></span>  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a><span data-ttu-id="fb226-152">“打印”对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-152">Print dialog box</span></span>

<span data-ttu-id="fb226-153">如下图中所示的打印对话框由打印功能用以选择和配置用户想要将数据打印到的打印机。</span><span class="sxs-lookup"><span data-stu-id="fb226-153">The print dialog box, shown in the following figure, is used by printing functionality to choose and configure the printer that a user would like to print data to.</span></span>  
  
![显示"打印"对话框的屏幕截图。](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
<span data-ttu-id="fb226-155">公共打印对话框作为<xref:System.Windows.Controls.PrintDialog>类实现，并位于命名空间中。 <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="fb226-155">The common print dialog box is implemented as the <xref:System.Windows.Controls.PrintDialog> class, and is located in the <xref:System.Windows.Controls> namespace.</span></span> <span data-ttu-id="fb226-156">以下代码显示了如何创建、配置和显示打印对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-156">The following code shows how to create, configure, and show one.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 <span data-ttu-id="fb226-157">有关打印对话框的详细信息，请参阅<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="fb226-157">For more information on the print dialog box, see <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fb226-158">有关 WPF 中打印的详细讨论，请参阅[打印概述](../advanced/printing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="fb226-158">For detailed discussion of printing in WPF, see [Printing Overview](../advanced/printing-overview.md).</span></span>  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a><span data-ttu-id="fb226-159">自定义对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-159">Custom dialog boxes</span></span>

<span data-ttu-id="fb226-160">尽管通用对话框很有用并应尽可能使用，但它们并不支持特定于域的对话框的要求。</span><span class="sxs-lookup"><span data-stu-id="fb226-160">While common dialog boxes are useful, and should be used when possible, they do not support the requirements of domain-specific dialog boxes.</span></span> <span data-ttu-id="fb226-161">在这些情况下，就需要创建自己的对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-161">In these cases, you need to create your own dialog boxes.</span></span> <span data-ttu-id="fb226-162">如我们所见，对话框是具有特殊行为的窗口。</span><span class="sxs-lookup"><span data-stu-id="fb226-162">As we'll see, a dialog box is a window with special behaviors.</span></span> <span data-ttu-id="fb226-163"><xref:System.Windows.Window>实现这些行为，因此，您用于<xref:System.Windows.Window>创建自定义模式和无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-163"><xref:System.Windows.Window> implements those behaviors and, consequently, you use <xref:System.Windows.Window> to create custom modal and modeless dialog boxes.</span></span>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a><span data-ttu-id="fb226-164">创建模式自定义对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-164">Creating a modal custom dialog box</span></span>

<span data-ttu-id="fb226-165">本主题演示如何使用<xref:System.Windows.Window>`Margins`对话框作为示例创建典型的模式对话框实现（请参阅[对话框示例](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)）。</span><span class="sxs-lookup"><span data-stu-id="fb226-165">This topic shows how to use <xref:System.Windows.Window> to create a typical modal dialog box implementation, using the `Margins` dialog box as an example (see [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)).</span></span> <span data-ttu-id="fb226-166">对话框`Margins`显示在下图中。</span><span class="sxs-lookup"><span data-stu-id="fb226-166">The `Margins` dialog box is shown in the following figure.</span></span>  
  
 ![带有用于定义边距、上边距、右边距和下边距的字段的边距对话框。](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a><span data-ttu-id="fb226-168">配置模式对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-168">Configuring a modal dialog box</span></span>

<span data-ttu-id="fb226-169">典型对话框的用户界面包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="fb226-169">The user interface for a typical dialog box includes the following:</span></span>  
  
- <span data-ttu-id="fb226-170">收集所需数据要求的各种控件。</span><span class="sxs-lookup"><span data-stu-id="fb226-170">The various controls that are required to gather the desired data.</span></span>  
  
- <span data-ttu-id="fb226-171">用户单击"**确定"** 按钮以关闭对话框、返回到函数并继续处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-171">An **OK** button that users click to close the dialog box, return to the function, and continue processing.</span></span>  
  
- <span data-ttu-id="fb226-172">用户单击的 **"取消"** 按钮以关闭对话框并停止该函数的进一步处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-172">A **Cancel** button that users click to close the dialog box and stop the function from further processing.</span></span>  
  
- <span data-ttu-id="fb226-173">标题栏中的 **"关闭**"按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-173">A **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="fb226-174">图标。</span><span class="sxs-lookup"><span data-stu-id="fb226-174">An icon.</span></span>  
  
- <span data-ttu-id="fb226-175">**最小化**、**最大化**和**还原**按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-175">**Minimize**, **Maximize**, and **Restore** buttons.</span></span>  
  
- <span data-ttu-id="fb226-176">用于**最小化**、最大化、还原和关闭对话框的系统菜单。</span><span class="sxs-lookup"><span data-stu-id="fb226-176">A **System** menu to minimize, maximize, restore, and close the dialog box.</span></span>  
  
- <span data-ttu-id="fb226-177">打开对话框的窗口上方和中心的位置。</span><span class="sxs-lookup"><span data-stu-id="fb226-177">A position above and in the center of the window that opened the dialog box.</span></span>  
  
- <span data-ttu-id="fb226-178">尽可能调整大小以防止对话框太小，并为用户提供有用的默认大小。</span><span class="sxs-lookup"><span data-stu-id="fb226-178">The ability to be resized where possible to prevent the dialog box from being too small, and to provide the user with a useful default size.</span></span> <span data-ttu-id="fb226-179">这要求您同时设置默认值和最小维度。</span><span class="sxs-lookup"><span data-stu-id="fb226-179">This requires that you set both the default and a minimum dimensions.</span></span>  
  
- <span data-ttu-id="fb226-180">ESC 键作为键盘快捷键，导致按下 **"取消"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-180">The ESC key as a keyboard shortcut that causes the **Cancel** button to be pressed.</span></span> <span data-ttu-id="fb226-181">为此，您可以将<xref:System.Windows.Controls.Button.IsCancel%2A>**"取消"** 按钮的属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="fb226-181">You do this by setting the <xref:System.Windows.Controls.Button.IsCancel%2A> property of the **Cancel** button to `true`.</span></span>  
  
- <span data-ttu-id="fb226-182">ENTER（或 RETURN）键作为键盘快捷键，用于按下 **"确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-182">The ENTER (or RETURN) key as a keyboard shortcut that causes the **OK** button to be pressed.</span></span> <span data-ttu-id="fb226-183">为此，您可以设置<xref:System.Windows.Controls.Button.IsDefault%2A>**"确定"** 按钮`true`的属性。</span><span class="sxs-lookup"><span data-stu-id="fb226-183">You do this by setting the <xref:System.Windows.Controls.Button.IsDefault%2A> property of the **OK** button `true`.</span></span>  
  
<span data-ttu-id="fb226-184">以下代码演示了这种配置。</span><span class="sxs-lookup"><span data-stu-id="fb226-184">The following code demonstrates this configuration.</span></span>  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
<span data-ttu-id="fb226-185">对话框用户体验还扩展到打开对话框的窗口菜单栏。</span><span class="sxs-lookup"><span data-stu-id="fb226-185">The user experience for a dialog box also extends into the menu bar of the window that opens the dialog box.</span></span> <span data-ttu-id="fb226-186">当菜单项运行需要用户通过对话框交互才能继续运行的函数时，函数的菜单项标题上会有一个省略号，如此处所示。</span><span class="sxs-lookup"><span data-stu-id="fb226-186">When a menu item runs a function that requires user interaction through a dialog box before the function can continue, the menu item for the function will have an ellipsis in its header, as shown here.</span></span>  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
<span data-ttu-id="fb226-187">当菜单项运行的函数显示无需用户交互的对话框（如“关于”对话框）时，则不需要省略号。</span><span class="sxs-lookup"><span data-stu-id="fb226-187">When a menu item runs a function that displays a dialog box which does not require user interaction, such as an About dialog box, an ellipsis is not required.</span></span>  
  
#### <a name="opening-a-modal-dialog-box"></a><span data-ttu-id="fb226-188">打开模式对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-188">Opening a modal dialog box</span></span>

<span data-ttu-id="fb226-189">对话框通常显示为用户选择菜单项来执行特定于域的函数的结果，比如在字处理器中设置文档边距。</span><span class="sxs-lookup"><span data-stu-id="fb226-189">A dialog box is typically shown as a result of a user selecting a menu item to perform a domain-specific function, such as setting the margins of a document in a word processor.</span></span> <span data-ttu-id="fb226-190">将窗口显示为对话框类似于显示普通窗口，只是它需要其他特定于对话框的配置。</span><span class="sxs-lookup"><span data-stu-id="fb226-190">Showing a window as a dialog box is similar to showing a normal window, although it requires additional dialog box-specific configuration.</span></span> <span data-ttu-id="fb226-191">以下代码中显示了实例化、配置和打开对话框的整个过程。</span><span class="sxs-lookup"><span data-stu-id="fb226-191">The entire process of instantiating, configuring, and opening a dialog box is shown in the following code.</span></span>  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

<span data-ttu-id="fb226-192">在这里，代码将默认信息（当前边距）传递给对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-192">Here, the code passes default information (the current margins) to the dialog box.</span></span> <span data-ttu-id="fb226-193">它还使用对显示<xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType>对话框的窗口的引用设置属性。</span><span class="sxs-lookup"><span data-stu-id="fb226-193">It also sets the <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> property with a reference to the window that is showing the dialog box.</span></span> <span data-ttu-id="fb226-194">通常，应始终设置对话框的所有者以提供所有对话框共有的窗口状态相关行为（有关详细信息，请参阅[WPF Windows 概述](wpf-windows-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="fb226-194">In general, you should always set the owner for a dialog box to provide window state-related behaviors that are common to all dialog boxes (see [WPF Windows Overview](wpf-windows-overview.md) for more information).</span></span>

> [!NOTE]
> <span data-ttu-id="fb226-195">您必须提供所有者以支持对话框的用户界面 （UI） 自动化（请参阅 UI[自动化概述](../../ui-automation/ui-automation-overview.md)）。</span><span class="sxs-lookup"><span data-stu-id="fb226-195">You must provide an owner to support user interface (UI) automation for dialog boxes (see [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).</span></span>

<span data-ttu-id="fb226-196">配置对话框后，通过调用<xref:System.Windows.Window.ShowDialog%2A>方法以模态方式显示该对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-196">After the dialog box is configured, it is shown modally by calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
#### <a name="validating-user-provided-data"></a><span data-ttu-id="fb226-197">验证用户提供的数据</span><span class="sxs-lookup"><span data-stu-id="fb226-197">Validating user-provided data</span></span>

<span data-ttu-id="fb226-198">当打开对话框并且用户提供所需数据时，对话框出于以下原因负责确保提供的数据有效：</span><span class="sxs-lookup"><span data-stu-id="fb226-198">When a dialog box is opened and the user provides the required data, a dialog box is responsible for ensuring that the provided data is valid for the following reasons:</span></span>  
  
- <span data-ttu-id="fb226-199">从安全角度，应该验证所有输入。</span><span class="sxs-lookup"><span data-stu-id="fb226-199">From a security perspective, all input should be validated.</span></span>  
  
- <span data-ttu-id="fb226-200">从特定于域的角度，数据验证可以防止代码处理错误数据，这可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="fb226-200">From a domain-specific perspective, data validation prevents erroneous data from being processed by the code, which could potentially throw exceptions.</span></span>  
  
- <span data-ttu-id="fb226-201">从用户体验角度，对话框可以帮助用户显示他们输入的哪些数据无效。</span><span class="sxs-lookup"><span data-stu-id="fb226-201">From a user-experience perspective, a dialog box can help users by showing them which data they have entered is invalid.</span></span>  
  
- <span data-ttu-id="fb226-202">从性能角度，多层应用程序中的数据验证可以减少客户端和应用程序层之间的往返次数，尤其当应用程序由 Web 服务或基于服务器的数据库构成时。</span><span class="sxs-lookup"><span data-stu-id="fb226-202">From a performance perspective, data validation in a multi-tier application can reduce the number of round trips between the client and the application tiers, particularly when the application is composed of Web services or server-based databases.</span></span>  

<span data-ttu-id="fb226-203">要验证 WPF 中的绑定控件，需要定义验证规则并将其与绑定相关联。</span><span class="sxs-lookup"><span data-stu-id="fb226-203">To validate a bound control in WPF, you need to define a validation rule and associate it with the binding.</span></span> <span data-ttu-id="fb226-204">验证规则是从 派生的自定义类<xref:System.Windows.Controls.ValidationRule>。</span><span class="sxs-lookup"><span data-stu-id="fb226-204">A validation rule is a custom class that derives from <xref:System.Windows.Controls.ValidationRule>.</span></span> <span data-ttu-id="fb226-205">下面的示例显示验证规则，`MarginValidationRule`该规则检查绑定值是否为 和<xref:System.Double>，并且在指定范围内。</span><span class="sxs-lookup"><span data-stu-id="fb226-205">The following example shows a validation rule, `MarginValidationRule`, which checks that a bound value is a <xref:System.Double> and is within a specified range.</span></span>  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

<span data-ttu-id="fb226-206">在此代码中，验证规则的验证逻辑是通过重写<xref:System.Windows.Controls.ValidationRule.Validate%2A>方法实现的，该方法验证数据并返回适当的<xref:System.Windows.Controls.ValidationResult>。</span><span class="sxs-lookup"><span data-stu-id="fb226-206">In this code, the validation logic of a validation rule is implemented by overriding the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method, which validates the data and returns an appropriate <xref:System.Windows.Controls.ValidationResult>.</span></span>  

<span data-ttu-id="fb226-207">要将验证规则与绑定控件进行关联，可以使用以下标记。</span><span class="sxs-lookup"><span data-stu-id="fb226-207">To associate the validation rule with the bound control, you use the following markup.</span></span>  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

<span data-ttu-id="fb226-208">关联验证规则后，WPF 将自动在将数据输入绑定控件时应用它。</span><span class="sxs-lookup"><span data-stu-id="fb226-208">Once the validation rule is associated, WPF will automatically apply it when data is entered into the bound control.</span></span> <span data-ttu-id="fb226-209">当控件包含无效数据时，WPF 将在无效控件周围显示红色边框，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="fb226-209">When a control contains invalid data, WPF will display a red border around the invalid control, as shown in the following figure.</span></span>  
  
![边距对话框，其红色边框围绕无效的左边距值。](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

<span data-ttu-id="fb226-211">WPF 不会将用户限制为无效控件，直到用户输入有效数据。</span><span class="sxs-lookup"><span data-stu-id="fb226-211">WPF does not restrict a user to the invalid control until they have entered valid data.</span></span> <span data-ttu-id="fb226-212">这对于对话框来说很好，无论数据是否有效用户都应该可以自由导航到对话框中的控件。</span><span class="sxs-lookup"><span data-stu-id="fb226-212">This is good behavior for a dialog box; a user should be able to freely navigate the controls in a dialog box whether or not data is valid.</span></span> <span data-ttu-id="fb226-213">但是，这意味着用户可以输入无效数据并按下 **"确定"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-213">However, this means a user can enter invalid data and press the **OK** button.</span></span> <span data-ttu-id="fb226-214">因此，当通过处理<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件按下 **"确定"** 按钮时，代码还需要验证对话框中的所有控件。</span><span class="sxs-lookup"><span data-stu-id="fb226-214">For this reason, your code also needs to validate all controls in a dialog box when the **OK** button is pressed by handling the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

<span data-ttu-id="fb226-215">此代码枚举窗口上的所有依赖项对象，如果任何依赖项对象无效（如<xref:System.Windows.Controls.Validation.GetHasError%2A>返回，无效控件获取焦点，`IsValid`则该方法返回`false`，并且窗口被视为无效。</span><span class="sxs-lookup"><span data-stu-id="fb226-215">This code enumerates all dependency objects on a window and, if any are invalid (as returned by <xref:System.Windows.Controls.Validation.GetHasError%2A>, the invalid control gets the focus, the `IsValid` method returns `false`, and the window is considered invalid.</span></span>  
  
<span data-ttu-id="fb226-216">一旦对话框有效，就可以安全关闭并返回。</span><span class="sxs-lookup"><span data-stu-id="fb226-216">Once a dialog box is valid, it can safely close and return.</span></span> <span data-ttu-id="fb226-217">作为返回过程的一部分，需要将结果返回到调用函数。</span><span class="sxs-lookup"><span data-stu-id="fb226-217">As part of the return process, it needs to return a result to the calling function.</span></span>  
  
#### <a name="setting-the-modal-dialog-result"></a><span data-ttu-id="fb226-218">设置模态对话框结果</span><span class="sxs-lookup"><span data-stu-id="fb226-218">Setting the modal dialog result</span></span>

<span data-ttu-id="fb226-219">使用<xref:System.Windows.Window.ShowDialog%2A>打开对话框从根本上说就像调用方法：使用<xref:System.Windows.Window.ShowDialog%2A>等待直到<xref:System.Windows.Window.ShowDialog%2A>返回打开对话框的代码。</span><span class="sxs-lookup"><span data-stu-id="fb226-219">Opening a dialog box using <xref:System.Windows.Window.ShowDialog%2A> is fundamentally like calling a method: the code that opened the dialog box using <xref:System.Windows.Window.ShowDialog%2A> waits until <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span> <span data-ttu-id="fb226-220">返回<xref:System.Windows.Window.ShowDialog%2A>时，调用它的代码需要根据用户是按下 **"确定"** 按钮还是 **"取消"** 按钮来决定是继续处理还是停止处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-220">When <xref:System.Windows.Window.ShowDialog%2A> returns, the code that called it needs to decide whether to continue processing or stop processing, based on whether the user pressed the **OK** button or the **Cancel** button.</span></span> <span data-ttu-id="fb226-221">为了便于做出此决策，该对话框需要将用户的选择作为从<xref:System.Boolean><xref:System.Windows.Window.ShowDialog%2A>方法返回的值返回。</span><span class="sxs-lookup"><span data-stu-id="fb226-221">To facilitate this decision, the dialog box needs to return the user's choice as a <xref:System.Boolean> value that is returned from the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  

<span data-ttu-id="fb226-222">单击 **"确定"** 按钮时，<xref:System.Windows.Window.ShowDialog%2A>应返回`true`。</span><span class="sxs-lookup"><span data-stu-id="fb226-222">When the **OK** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `true`.</span></span> <span data-ttu-id="fb226-223">这是通过在单击<xref:System.Windows.Window.DialogResult%2A>**"确定"** 按钮时设置对话框的属性来实现的。</span><span class="sxs-lookup"><span data-stu-id="fb226-223">This is achieved by setting the <xref:System.Windows.Window.DialogResult%2A> property of the dialog box when the **OK** button is clicked.</span></span>  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

<span data-ttu-id="fb226-224">请注意，设置<xref:System.Windows.Window.DialogResult%2A>属性还会导致窗口自动关闭，这减轻了显式调用<xref:System.Windows.Window.Close%2A>的需要。</span><span class="sxs-lookup"><span data-stu-id="fb226-224">Note that setting the <xref:System.Windows.Window.DialogResult%2A> property also causes the window to close automatically, which alleviates the need to explicitly call <xref:System.Windows.Window.Close%2A>.</span></span>  
  
<span data-ttu-id="fb226-225">单击 **"取消"** 按钮时，<xref:System.Windows.Window.ShowDialog%2A>应返回`false`，这还需要设置<xref:System.Windows.Window.DialogResult%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fb226-225">When the **Cancel** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `false`, which also requires setting the <xref:System.Windows.Window.DialogResult%2A> property.</span></span>  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

<span data-ttu-id="fb226-226">当按钮的属性<xref:System.Windows.Controls.Button.IsCancel%2A>设置为`true`，并且用户按下 **"取消"** 按钮或 ESC 键时，<xref:System.Windows.Window.DialogResult%2A>将自动设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="fb226-226">When a button's <xref:System.Windows.Controls.Button.IsCancel%2A> property is set to `true` and the user presses either the **Cancel** button or the ESC key, <xref:System.Windows.Window.DialogResult%2A> is automatically set to `false`.</span></span> <span data-ttu-id="fb226-227">以下标记的效果与前面的代码相同，无需处理事件<xref:System.Windows.Controls.Primitives.ButtonBase.Click>。</span><span class="sxs-lookup"><span data-stu-id="fb226-227">The following markup has the same effect as the preceding code, without the need to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

<span data-ttu-id="fb226-228">当用户按下标题栏中的`false`**"关闭"** 按钮或从 **"系统**"菜单中选择"**关闭**"菜单项时，将自动返回一个对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-228">A dialog box automatically returns `false` when a user presses the **Close** button in the title bar or chooses the **Close** menu item from the **System** menu.</span></span>  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a><span data-ttu-id="fb226-229">处理从模式对话框返回的数据</span><span class="sxs-lookup"><span data-stu-id="fb226-229">Processing data returned from a modal dialog box</span></span>  

<span data-ttu-id="fb226-230">当<xref:System.Windows.Window.DialogResult%2A>由对话框设置时，打开它的函数可以通过在返回时<xref:System.Windows.Window.DialogResult%2A><xref:System.Windows.Window.ShowDialog%2A>检查该属性来获取对话框的结果。</span><span class="sxs-lookup"><span data-stu-id="fb226-230">When <xref:System.Windows.Window.DialogResult%2A> is set by a dialog box, the function that opened it can get the dialog box result by inspecting the <xref:System.Windows.Window.DialogResult%2A> property when <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span>  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

<span data-ttu-id="fb226-231">如果对话框结果是`true`，则函数将该结果用作检索和处理用户提供的数据的提示。</span><span class="sxs-lookup"><span data-stu-id="fb226-231">If the dialog result is `true`, the function uses that as a cue to retrieve and process the data provided by the user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb226-232">返回<xref:System.Windows.Window.ShowDialog%2A>后，无法重新打开对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-232">After <xref:System.Windows.Window.ShowDialog%2A> has returned, a dialog box cannot be reopened.</span></span> <span data-ttu-id="fb226-233">相反，需要创建新实例。</span><span class="sxs-lookup"><span data-stu-id="fb226-233">Instead, you need to create a new instance.</span></span>

<span data-ttu-id="fb226-234">如果对话框结果是`false`，则函数应适当地结束处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-234">If the dialog result is `false`, the function should end processing appropriately.</span></span>  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a><span data-ttu-id="fb226-235">创建无模式自定义对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-235">Creating a modeless custom dialog box</span></span>

<span data-ttu-id="fb226-236">无模式对话框（如下图中所示的“查找”对话框）与模式对话框具有相同的基本外观。</span><span class="sxs-lookup"><span data-stu-id="fb226-236">A modeless dialog box, such as the Find Dialog Box shown in the following figure, has the same fundamental appearance as the modal dialog box.</span></span>  

![显示"查找"对话框的屏幕截图。](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

<span data-ttu-id="fb226-238">但行为稍有不同，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="fb226-238">However, the behavior is slightly different, as described in the following sections.</span></span>  
  
#### <a name="opening-a-modeless-dialog-box"></a><span data-ttu-id="fb226-239">打开无模式对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-239">Opening a modeless dialog box</span></span>

<span data-ttu-id="fb226-240">通过调用<xref:System.Windows.Window.Show%2A>方法打开无模式对话框。</span><span class="sxs-lookup"><span data-stu-id="fb226-240">A modeless dialog box is opened by calling the <xref:System.Windows.Window.Show%2A> method.</span></span>  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

<span data-ttu-id="fb226-241">不像<xref:System.Windows.Window.ShowDialog%2A> <xref:System.Windows.Window.Show%2A> ，立即返回。</span><span class="sxs-lookup"><span data-stu-id="fb226-241">Unlike <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> returns immediately.</span></span> <span data-ttu-id="fb226-242">因此，调用窗口无法判断无模式对话框何时关闭，也就不知道何时检查对话框结果或从对话框获取数据进行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-242">Consequently, the calling window cannot tell when the modeless dialog box is closed and, therefore, does not know when to check for a dialog box result or get data from the dialog box for further processing.</span></span> <span data-ttu-id="fb226-243">相反，对话框需要创建替代方法来将数据返回到调用窗口进行处理。</span><span class="sxs-lookup"><span data-stu-id="fb226-243">Instead, the dialog box needs to create an alternative way to return data to the calling window for processing.</span></span>  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a><span data-ttu-id="fb226-244">处理从无模式对话框返回的数据</span><span class="sxs-lookup"><span data-stu-id="fb226-244">Processing data returned from a modeless dialog box</span></span>  

<span data-ttu-id="fb226-245">在此示例中，`FindDialogBox`可能会将一个或多个查找结果返回给主窗口，具体取决于搜索的文本，而不带任何特定频率。</span><span class="sxs-lookup"><span data-stu-id="fb226-245">In this example, the `FindDialogBox` may return one or more find results to the main window, depending on the text being searched for without any specific frequency.</span></span> <span data-ttu-id="fb226-246">和模式对话框一样，无模式对话框也可以使用属性返回结果。</span><span class="sxs-lookup"><span data-stu-id="fb226-246">As with a modal dialog box, a modeless dialog box can return results using properties.</span></span> <span data-ttu-id="fb226-247">但拥有对话框的窗口需要了解何时检查那些属性。</span><span class="sxs-lookup"><span data-stu-id="fb226-247">However, the window that owns the dialog box needs to know when to check those properties.</span></span> <span data-ttu-id="fb226-248">实现此目的的一种方法是用对话框实现事件，只要找到文本就引发它。</span><span class="sxs-lookup"><span data-stu-id="fb226-248">One way to enable this is for the dialog box to implement an event that is raised whenever text is found.</span></span> <span data-ttu-id="fb226-249">`FindDialogBox`实现`TextFoundEvent`为此目的，首先需要委托。</span><span class="sxs-lookup"><span data-stu-id="fb226-249">`FindDialogBox` implements the `TextFoundEvent` for this purpose, which first requires a delegate.</span></span>  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

<span data-ttu-id="fb226-250">使用`TextFoundEventHandler`委托实现`FindDialogBox`。 `TextFoundEvent`</span><span class="sxs-lookup"><span data-stu-id="fb226-250">Using the `TextFoundEventHandler` delegate, `FindDialogBox` implements the `TextFoundEvent`.</span></span>
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

<span data-ttu-id="fb226-251">因此，`Find`当找到搜索结果时，可以引发事件。</span><span class="sxs-lookup"><span data-stu-id="fb226-251">Consequently, `Find` can raise the event when a search result is found.</span></span>  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

<span data-ttu-id="fb226-252">所有者窗口则需要注册和处理此事件。</span><span class="sxs-lookup"><span data-stu-id="fb226-252">The owner window then needs to register with and handle this event.</span></span>

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a><span data-ttu-id="fb226-253">关闭无模式对话框</span><span class="sxs-lookup"><span data-stu-id="fb226-253">Closing a modeless dialog box</span></span>

<span data-ttu-id="fb226-254">由于<xref:System.Windows.Window.DialogResult%2A>不需要设置，因此可以使用系统提供机制关闭无模式对话框，包括：</span><span class="sxs-lookup"><span data-stu-id="fb226-254">Because <xref:System.Windows.Window.DialogResult%2A> does not need to be set, a modeless dialog can be closed using system provide mechanisms, including the following:</span></span>  
  
- <span data-ttu-id="fb226-255">单击标题栏中的 **"关闭**"按钮。</span><span class="sxs-lookup"><span data-stu-id="fb226-255">Clicking the **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="fb226-256">按 ALT+F4。</span><span class="sxs-lookup"><span data-stu-id="fb226-256">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="fb226-257">从 **"系统**"菜单中选择 **"关闭**"。</span><span class="sxs-lookup"><span data-stu-id="fb226-257">Choosing **Close** from the **System** menu.</span></span>  
  
<span data-ttu-id="fb226-258">或者，当单击"<xref:System.Windows.Window.Close%2A>**关闭**"按钮时，代码可以调用。</span><span class="sxs-lookup"><span data-stu-id="fb226-258">Alternatively, your code can call <xref:System.Windows.Window.Close%2A> when the **Close** button is clicked.</span></span>  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a><span data-ttu-id="fb226-259">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb226-259">See also</span></span>

- [<span data-ttu-id="fb226-260">Popup 概述</span><span class="sxs-lookup"><span data-stu-id="fb226-260">Popup Overview</span></span>](../controls/popup-overview.md)
- [<span data-ttu-id="fb226-261">对话框示例</span><span class="sxs-lookup"><span data-stu-id="fb226-261">Dialog Box Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
