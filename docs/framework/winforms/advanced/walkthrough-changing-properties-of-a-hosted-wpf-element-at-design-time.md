---
title: 演练：设计时更改承载的 WPF 元素的属性
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], changing properties at design time
- Windows Forms, changing properties of WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- interoperability [WPF]
ms.assetid: a1f7a90c-0bbb-4781-8c3c-8cc8bef2488d
ms.openlocfilehash: d17273f52d0cef118b79fef03af72522f6677073
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529816"
---
# <a name="walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time"></a><span data-ttu-id="e9f20-102">演练：设计时更改承载的 WPF 元素的属性</span><span class="sxs-lookup"><span data-stu-id="e9f20-102">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>
<span data-ttu-id="e9f20-103">本演练展示了如何更改 Windows 窗体上承载的 Windows Presentation Foundation (WPF) 控件的属性值。</span><span class="sxs-lookup"><span data-stu-id="e9f20-103">This walkthrough shows you how to change property values of a Windows Presentation Foundation (WPF) control hosted on a Windows Form.</span></span>  
  
 <span data-ttu-id="e9f20-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e9f20-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="e9f20-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-105">Create the project.</span></span>  
  
-   <span data-ttu-id="e9f20-106">创建 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="e9f20-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="e9f20-107">在 Windows 窗体上承载 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="e9f20-107">Host the WPF controls on a Windows Form.</span></span>  
  
-   <span data-ttu-id="e9f20-108">使用 Visual Studio 的 WPF 设计器来更改属性值。</span><span class="sxs-lookup"><span data-stu-id="e9f20-108">Use the WPF Designer for Visual Studio to change property values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9f20-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="e9f20-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e9f20-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="e9f20-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e9f20-111">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="e9f20-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e9f20-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="e9f20-112">Prerequisites</span></span>  
 <span data-ttu-id="e9f20-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="e9f20-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="e9f20-114">。</span><span class="sxs-lookup"><span data-stu-id="e9f20-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="e9f20-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="e9f20-115">Creating the Project</span></span>  
 <span data-ttu-id="e9f20-116">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e9f20-117">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="e9f20-118">要创建项目</span><span class="sxs-lookup"><span data-stu-id="e9f20-118">To create the project</span></span>  
  
-   <span data-ttu-id="e9f20-119">创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`WpfHost`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `WpfHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="e9f20-120">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-120">Creating the WPF Control</span></span>  
 <span data-ttu-id="e9f20-121">将 WPF 控件添加到项目后，就可以在窗体上对其进行排列。</span><span class="sxs-lookup"><span data-stu-id="e9f20-121">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="e9f20-122">创建 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-122">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="e9f20-123">将新的 WPF <xref:System.Windows.Controls.UserControl> 添加到项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-123">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="e9f20-124">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-124">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="e9f20-125">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="e9f20-125">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="e9f20-126">在**属性**窗口中，设置的值<xref:System.Windows.Controls.Control.Background%2A>属性`Blue`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-126">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
3.  <span data-ttu-id="e9f20-127">生成项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-127">Build the project.</span></span>  
  
## <a name="changing-property-values-on-the-wpf-control"></a><span data-ttu-id="e9f20-128">在 WPF 控件上更改属性值</span><span class="sxs-lookup"><span data-stu-id="e9f20-128">Changing Property Values on the WPF Control</span></span>  
 <span data-ttu-id="e9f20-129">通过使用 WPF 设计器，<xref:System.Windows.Forms.Integration.ElementHost> 智能标记使更改承载的 WPF 内容的属性变得轻松。</span><span class="sxs-lookup"><span data-stu-id="e9f20-129">The <xref:System.Windows.Forms.Integration.ElementHost> smart tag makes it easy to change properties of hosted WPF content by using the WPF Designer.</span></span>  
  
#### <a name="to-host-a-wpf-control"></a><span data-ttu-id="e9f20-130">承载 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-130">To host a WPF control</span></span>  
  
1.  <span data-ttu-id="e9f20-131">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-131">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="e9f20-132">在**工具箱**中**WPF 用户控件**选项卡上，双击`UserControl1`若要创建的实例`UserControl1`窗体上。</span><span class="sxs-lookup"><span data-stu-id="e9f20-132">In the **Toolbox**, in the **WPF User Controls** tab, double-click `UserControl1` to create an instance of `UserControl1` on the form.</span></span>  
  
     <span data-ttu-id="e9f20-133">`UserControl1` 的实例承载在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="e9f20-133">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
3.  <span data-ttu-id="e9f20-134">在**ElementHost 任务**智能标记面板中，选择**编辑所承载的内容**。</span><span class="sxs-lookup"><span data-stu-id="e9f20-134">In the **ElementHost Tasks** smart tag panel, select **Edit Hosted Content**.</span></span>  
  
     <span data-ttu-id="e9f20-135">UserControl1.xaml 在 WPF 设计器中随即打开。</span><span class="sxs-lookup"><span data-stu-id="e9f20-135">UserControl1.xaml opens in the WPF Designer.</span></span>  
  
4.  <span data-ttu-id="e9f20-136">在**属性**窗口中，设置的值<xref:System.Windows.Controls.Control.Background%2A>属性`Red`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-136">In the **Properties** window, set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Red`.</span></span>  
  
5.  <span data-ttu-id="e9f20-137">重新生成项目。</span><span class="sxs-lookup"><span data-stu-id="e9f20-137">Rebuild the project.</span></span>  
  
6.  <span data-ttu-id="e9f20-138">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="e9f20-138">Open `Form1` in the Windows Forms Designer.</span></span>  
  
     <span data-ttu-id="e9f20-139">`UserControl1` 的实例具有红色背景。</span><span class="sxs-lookup"><span data-stu-id="e9f20-139">The instance of `UserControl1` has a red background.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f20-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9f20-140">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="e9f20-141">如何：在 TableLayoutPanel 控件中锚定和停靠子控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-141">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="e9f20-142">如何：设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="e9f20-142">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="e9f20-143">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-143">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="e9f20-144">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="e9f20-144">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="e9f20-145">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="e9f20-145">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="e9f20-146">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="e9f20-146">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
