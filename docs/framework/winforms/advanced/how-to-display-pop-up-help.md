---
title: 如何：显示弹出帮助
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: 47833e734c09e402ab1824b9c629b2ba39acfb9f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44076372"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="0a928-102">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="0a928-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="0a928-103">若要在 Windows 窗体上显示帮助的一种方法是通过**帮助**按钮，位于标题栏，可通过访问右侧<xref:System.Windows.Forms.Form.HelpButton%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0a928-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="0a928-104">此类型的“帮助”显示非常适用于对话框。</span><span class="sxs-lookup"><span data-stu-id="0a928-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="0a928-105">使用 <xref:System.Windows.Forms.Form.ShowDialog%2A> 方法适度显示的对话框在获取外部帮助系统时会遇到问题，因为必须先关闭模型对话框后才能切换到另一个窗口。</span><span class="sxs-lookup"><span data-stu-id="0a928-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="0a928-106">此外，使用**帮助**按钮，则需要无**最小化**按钮或**最大化**按钮的标题栏中所示。</span><span class="sxs-lookup"><span data-stu-id="0a928-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="0a928-107">这是一个标准对话框约定，而窗体通常具有**最小化**并**最大化**按钮。</span><span class="sxs-lookup"><span data-stu-id="0a928-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="0a928-108">请注意，你还可以使用 <xref:System.Windows.Forms.HelpProvider> 组件将控件链接到帮助系统中的文件，即使你已实现了弹出帮助。</span><span class="sxs-lookup"><span data-stu-id="0a928-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="0a928-109">有关详细信息，请参阅[Windows 应用程序中提供帮助](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)。</span><span class="sxs-lookup"><span data-stu-id="0a928-109">For more information, see [Providing Help in a Windows Application](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a928-110">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="0a928-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0a928-111">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="0a928-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0a928-112">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="0a928-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="0a928-113">显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="0a928-113">To display pop-up Help</span></span>  
  
1.  <span data-ttu-id="0a928-114">拖动[HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)组件从工具箱拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="0a928-114">Drag a [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="0a928-115">它将显示在 Windows 窗体设计器底部的任务栏中。</span><span class="sxs-lookup"><span data-stu-id="0a928-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="0a928-116">在“属性”窗口，将 <xref:System.Windows.Forms.Form.HelpButton%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0a928-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="0a928-117">这将在窗体的标题栏右侧显示带问号的按钮。</span><span class="sxs-lookup"><span data-stu-id="0a928-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3.  <span data-ttu-id="0a928-118">为了显示 <xref:System.Windows.Forms.Form.HelpButton%2A>，必须将窗体的 <xref:System.Windows.Forms.Form.MinimizeBox%2A> 和 <xref:System.Windows.Forms.Form.MaximizeBox%2A> 属性设置为 `false`，将 <xref:System.Windows.Forms.Form.ControlBox%2A> 属性设置为 `true` 以及将 <xref:System.Windows.Forms.Form.FormBorderStyle%2A> 属性设置为下列值之一：<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog> 或 <xref:System.Windows.Forms.FormBorderStyle.Sizable>。</span><span class="sxs-lookup"><span data-stu-id="0a928-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4.  <span data-ttu-id="0a928-119">选择想在你的窗体上显示帮助的控件，然后在“属性”窗口设置“帮助”字符串。</span><span class="sxs-lookup"><span data-stu-id="0a928-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="0a928-120">这是将类似于窗口中显示的文本的字符串[工具提示](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="0a928-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md).</span></span>  
  
5.  <span data-ttu-id="0a928-121">按 F5 。</span><span class="sxs-lookup"><span data-stu-id="0a928-121">Press **F5**.</span></span>  
  
6.  <span data-ttu-id="0a928-122">按**帮助**按钮的标题栏上，单击设置帮助字符串的控件。</span><span class="sxs-lookup"><span data-stu-id="0a928-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a928-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a928-123">See Also</span></span>  
 [<span data-ttu-id="0a928-124">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="0a928-124">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 [<span data-ttu-id="0a928-125">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="0a928-125">Integrating User Help in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/integrating-user-help-in-windows-forms.md)  
 [<span data-ttu-id="0a928-126">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="0a928-126">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
