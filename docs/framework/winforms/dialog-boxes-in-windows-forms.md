---
title: Windows 窗体中的对话框
ms.date: 03/30/2017
helpviewer_keywords:
- dialog boxes [Windows Forms], Windows Forms
- Windows Forms dialog boxes
- dialogs [Windows Forms], using in Windows Forms
ms.assetid: d43d022b-451b-490d-9386-dc79d98fbf8a
ms.openlocfilehash: 302e59c607f179869bcf3923c3092e73a1eddc91
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539898"
---
# <a name="dialog-boxes-in-windows-forms"></a><span data-ttu-id="71f63-102">Windows 窗体中的对话框</span><span class="sxs-lookup"><span data-stu-id="71f63-102">Dialog Boxes in Windows Forms</span></span>
<span data-ttu-id="71f63-103">对话框用于与用户交互和检索信息。</span><span class="sxs-lookup"><span data-stu-id="71f63-103">Dialog boxes are used to interact with the user and retrieve information.</span></span> <span data-ttu-id="71f63-104">简单地说，对话框是将其 <xref:System.Windows.Forms.FormBorderStyle> 枚举属性设置为 `FixedDialog` 的窗体。</span><span class="sxs-lookup"><span data-stu-id="71f63-104">In simple terms, a dialog box is a form with its <xref:System.Windows.Forms.FormBorderStyle> enumeration property set to `FixedDialog`.</span></span> <span data-ttu-id="71f63-105">您可以通过使用 Visual Studio 中的 Windows 窗体设计器来构造你自己的自定义对话框。</span><span class="sxs-lookup"><span data-stu-id="71f63-105">You can construct your own custom dialog boxes by using the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="71f63-106">添加 `Label`、`Textbox` 和 `Button` 等控件，以便根据你的特定需求自定义对话框。</span><span class="sxs-lookup"><span data-stu-id="71f63-106">Add controls such as `Label`, `Textbox`, and `Button` to customize dialog boxes to your specific needs.</span></span> <span data-ttu-id="71f63-107">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]还包括预定义的对话框框中，如**文件打开**和消息框，你可以调整为你自己的应用程序。</span><span class="sxs-lookup"><span data-stu-id="71f63-107">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also includes predefined dialog boxes, such as **File Open** and message boxes, which you can adapt for your own applications.</span></span> <span data-ttu-id="71f63-108">有关详细信息，请参阅[对话框控件和组件](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="71f63-108">For more information, see [Dialog-Box Controls and Components](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="71f63-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="71f63-109">In This Section</span></span>  
 [<span data-ttu-id="71f63-110">如何：显示 Windows 窗体的对话框</span><span class="sxs-lookup"><span data-stu-id="71f63-110">How to: Display Dialog Boxes for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-display-dialog-boxes-for-windows-forms.md)  
 <span data-ttu-id="71f63-111">提供有关显示对话框的指示。</span><span class="sxs-lookup"><span data-stu-id="71f63-111">Gives directions for showing dialog boxes.</span></span>  
  
-   <span data-ttu-id="71f63-112">[如何： 检索对话框信息有选择地使用多个属性](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-112">[How to: Retrieve Dialog Box Information Selectively Using Multiple Properties](http://msdn.microsoft.com/library/56taefba\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-113">[如何： 从对话框中的父窗体检索信息](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-113">[How to: Retrieve Information from the Parent Form of a Dialog Box](http://msdn.microsoft.com/library/k70t19bb\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-114">[用户输入到对话框](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-114">[User Input to Dialog Boxes](http://msdn.microsoft.com/library/1s9ws53w\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-115">[如何： 检索对话框中的结果](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-115">[How to: Retrieve the Result for Dialog Boxes](http://msdn.microsoft.com/library/40x40td1\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-116">[演练： 检索对话框信息使用对象整体](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-116">[Walkthrough: Retrieving Dialog Box Information Collectively Using Objects](http://msdn.microsoft.com/library/cakx2hdw\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-117">[如何： 关闭对话框并保留用户输入](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-117">[How to: Close Dialog Boxes and Retain User Input](http://msdn.microsoft.com/library/65ad5907\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-118">[如何： 在设计时创建对话框](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-118">[How to: Create Dialog Boxes at Design Time](http://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="71f63-119">[如何： 显示消息框](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="71f63-119">[How to: Display Message Boxes](http://msdn.microsoft.com/library/3tt9e94f\(v=vs.110\))</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="71f63-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="71f63-120">Related Sections</span></span>  
 [<span data-ttu-id="71f63-121">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="71f63-121">Dialog-Box Controls and Components</span></span>](../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 <span data-ttu-id="71f63-122">列出预定义的对话框控件。</span><span class="sxs-lookup"><span data-stu-id="71f63-122">Lists the predefined dialog box controls.</span></span>  
  
 [<span data-ttu-id="71f63-123">更改 Windows 窗体外观</span><span class="sxs-lookup"><span data-stu-id="71f63-123">Changing the Appearance of Windows Forms</span></span>](../../../docs/framework/winforms/changing-the-appearance-of-windows-forms.md)  
 <span data-ttu-id="71f63-124">包含介绍如何更改 Windows 窗体应用程序外观的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="71f63-124">Contains links to topics that describe how to change the appearance of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="71f63-125">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="71f63-125">TabControl Control Overview</span></span>](../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 <span data-ttu-id="71f63-126">说明如何将选项卡控件合并到一个对话框中。</span><span class="sxs-lookup"><span data-stu-id="71f63-126">Explains how you incorporate the tab control into a dialog box.</span></span>
