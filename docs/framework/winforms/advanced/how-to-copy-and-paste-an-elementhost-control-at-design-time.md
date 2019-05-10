---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211393"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="4a9e3-102">如何：在设计时复制并粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="4a9e3-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>

<span data-ttu-id="4a9e3-103">此过程演示如何在 Visual Studio 中复制在 Windows 窗体上的 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="4a9e3-104">复制并粘贴 ElementHost 控件在设计时</span><span class="sxs-lookup"><span data-stu-id="4a9e3-104">Copy and paste an ElementHost control at design time</span></span>

1. <span data-ttu-id="4a9e3-105">添加新的 WPF<xref:System.Windows.Controls.UserControl>到 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-105">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="4a9e3-106">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-106">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="4a9e3-107">有关详细信息，请参见[演练：在设计时在 Windows 窗体上创建新的 WPF 内容](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-107">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="4a9e3-108">在中**属性**窗口中，设置的值<xref:System.Windows.FrameworkElement.Width%2A>并<xref:System.Windows.FrameworkElement.Height%2A>的属性`UserControl1`到`200`。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-108">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>

3. <span data-ttu-id="4a9e3-109">将 <xref:System.Windows.Controls.Control.Background%2A> 属性的值设置为 `Blue`。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-109">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

4. <span data-ttu-id="4a9e3-110">生成项目。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-110">Build the project.</span></span>

5. <span data-ttu-id="4a9e3-111">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-111">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="4a9e3-112">从**工具箱**，将拖动的一个实例`UserControl1`拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-112">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="4a9e3-113">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-113">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="4a9e3-114">选择`elementHost1` 后，按 CTRL + C 将它复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-114">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>

8. <span data-ttu-id="4a9e3-115">按 CTRL + V 粘贴复制的控件拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-115">Press CTRL+V to paste the copied control onto the form.</span></span>

   <span data-ttu-id="4a9e3-116">一个新<xref:System.Windows.Forms.Integration.ElementHost>名为控件`elementHost2`窗体上创建。</span><span class="sxs-lookup"><span data-stu-id="4a9e3-116">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a9e3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a9e3-117">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="4a9e3-118">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="4a9e3-118">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="4a9e3-119">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="4a9e3-119">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="4a9e3-120">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="4a9e3-120">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
