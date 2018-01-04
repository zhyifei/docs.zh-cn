---
title: "如何：在设计时复制并粘贴 ElementHost 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe7d050de84eba8c7962a62a8604a72f78bc2bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="79aed-102">如何：在设计时复制并粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="79aed-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>
<span data-ttu-id="79aed-103">此过程演示如何复制 Windows 窗体上的 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="79aed-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79aed-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="79aed-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="79aed-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="79aed-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="79aed-106">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="79aed-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="79aed-107">复制和粘贴 ElementHost 控件在设计时</span><span class="sxs-lookup"><span data-stu-id="79aed-107">To copy and paste an ElementHost control at design time</span></span>  
  
1.  <span data-ttu-id="79aed-108">添加新的 WPF<xref:System.Windows.Controls.UserControl>到你的 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="79aed-108">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="79aed-109">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="79aed-109">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="79aed-110">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="79aed-110">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="79aed-111">在**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性`UserControl1`到`200`。</span><span class="sxs-lookup"><span data-stu-id="79aed-111">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>  
  
3.  <span data-ttu-id="79aed-112">将 <xref:System.Windows.Controls.Control.Background%2A> 属性的值设置为 `Blue`。</span><span class="sxs-lookup"><span data-stu-id="79aed-112">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
4.  <span data-ttu-id="79aed-113">生成项目。</span><span class="sxs-lookup"><span data-stu-id="79aed-113">Build the project.</span></span>  
  
5.  <span data-ttu-id="79aed-114">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="79aed-114">Open `Form1` in the Windows Forms Designer.</span></span>  
  
6.  <span data-ttu-id="79aed-115">从**工具箱**的一个实例拖`UserControl1`拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="79aed-115">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="79aed-116">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="79aed-116">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
7.  <span data-ttu-id="79aed-117">选择`elementHost1` 后，按 CTRL + C 将它复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="79aed-117">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
8.  <span data-ttu-id="79aed-118">按 CTRL + V 粘贴复制的控件拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="79aed-118">Press CTRL+V to paste the copied control onto the form.</span></span>  
  
     <span data-ttu-id="79aed-119">一个新<xref:System.Windows.Forms.Integration.ElementHost>控件名为`elementHost2`在窗体上创建。</span><span class="sxs-lookup"><span data-stu-id="79aed-119">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79aed-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="79aed-120">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="79aed-121">演练：将 ElementHost 控件复制并粘贴到各个 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="79aed-121">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 [<span data-ttu-id="79aed-122">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="79aed-122">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="79aed-123">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="79aed-123">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="79aed-124">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="79aed-124">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
