---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: a61a8538fb9b4245e3f3705c5d5cbb1b45ed0b72
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47233213"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="339b0-102">如何：在设计时复制并粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="339b0-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="339b0-103">此过程演示如何将复制在 Windows 窗体上的 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="339b0-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="339b0-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="339b0-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="339b0-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="339b0-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="339b0-106">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="339b0-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="339b0-107">若要复制并粘贴 ElementHost 控件在设计时</span><span class="sxs-lookup"><span data-stu-id="339b0-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="339b0-108">添加新的 WPF<xref:System.Windows.Controls.UserControl>到 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="339b0-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="339b0-109">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="339b0-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="339b0-110">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="339b0-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="339b0-111">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>的属性`UserControl1`到`200`。</span><span class="sxs-lookup"><span data-stu-id="339b0-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="339b0-112">将 <xref:System.Windows.Controls.Control.Background%2A> 属性的值设置为 `Blue`。</span><span class="sxs-lookup"><span data-stu-id="339b0-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="339b0-113">生成项目。</span><span class="sxs-lookup"><span data-stu-id="339b0-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="339b0-114">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="339b0-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="339b0-115">从**工具箱**，将拖动的一个实例`UserControl1`拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="339b0-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="339b0-116">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="339b0-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="339b0-117">选择`elementHost1` 后，按 CTRL + C 将它复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="339b0-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="339b0-118">按 CTRL + V 粘贴复制的控件拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="339b0-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="339b0-119">一个新<xref:System.Windows.Forms.Integration.ElementHost>名为控件`elementHost2`窗体上创建。</span><span class="sxs-lookup"><span data-stu-id="339b0-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="339b0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="339b0-120">See Also</span></span>  

- <xref:System.Windows.Forms.Integration.ElementHost>  
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
- [<span data-ttu-id="339b0-121">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="339b0-121">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
- [<span data-ttu-id="339b0-122">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="339b0-122">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
- [<span data-ttu-id="339b0-123">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="339b0-123">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)