---
title: 如何：在设计时复制并粘贴 ElementHost 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfe5244e0c5b61fdf6d940dd16d8c280f013b12c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666183"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a><span data-ttu-id="fc30d-102">如何：复制并粘贴 ElementHost 控件</span><span class="sxs-lookup"><span data-stu-id="fc30d-102">How to: Copy and paste an ElementHost control</span></span>

<span data-ttu-id="fc30d-103">此过程演示如何在 Visual Studio 中的 Windows 窗体上复制 Windows Presentation Foundation (WPF) 控件。</span><span class="sxs-lookup"><span data-stu-id="fc30d-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

1. <span data-ttu-id="fc30d-104">在 Visual Studio 中, 将一个新<xref:System.Windows.Controls.UserControl>的 WPF 添加到 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="fc30d-104">In Visual Studio, add a new WPF <xref:System.Windows.Controls.UserControl> to a Windows Forms project.</span></span> <span data-ttu-id="fc30d-105">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="fc30d-105">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="fc30d-106">有关详细信息，请参见[演练：在设计时](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)在 Windows 窗体上创建新的 WPF 内容。</span><span class="sxs-lookup"><span data-stu-id="fc30d-106">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="fc30d-107">在 "**属性**" 窗口中<xref:System.Windows.FrameworkElement.Width%2A> , 将的和<xref:System.Windows.FrameworkElement.Height%2A>属性`UserControl1`的值设置为**200**。</span><span class="sxs-lookup"><span data-stu-id="fc30d-107">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to **200**.</span></span>

3. <span data-ttu-id="fc30d-108">将<xref:System.Windows.Controls.Control.Background%2A>属性的值设置为**蓝色**。</span><span class="sxs-lookup"><span data-stu-id="fc30d-108">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to **Blue**.</span></span>

4. <span data-ttu-id="fc30d-109">生成项目。</span><span class="sxs-lookup"><span data-stu-id="fc30d-109">Build the project.</span></span>

5. <span data-ttu-id="fc30d-110">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="fc30d-110">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="fc30d-111">从 "**工具箱**" 中, 将的`UserControl1`实例拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="fc30d-111">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="fc30d-112">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="fc30d-112">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="fc30d-113">选中此选项后, 按**Ctrl**+C 将其复制到剪贴板。 `elementHost1`</span><span class="sxs-lookup"><span data-stu-id="fc30d-113">With `elementHost1` selected, press **Ctrl**+**C** to copy it to the clipboard.</span></span>

8. <span data-ttu-id="fc30d-114">按**Ctrl**+**V**将复制的控件粘贴到窗体上。</span><span class="sxs-lookup"><span data-stu-id="fc30d-114">Press **Ctrl**+**V** to paste the copied control onto the form.</span></span>

   <span data-ttu-id="fc30d-115">在窗<xref:System.Windows.Forms.Integration.ElementHost>体上`elementHost2`创建一个名为的新控件。</span><span class="sxs-lookup"><span data-stu-id="fc30d-115">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc30d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc30d-116">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="fc30d-117">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="fc30d-117">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="fc30d-118">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="fc30d-118">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="fc30d-119">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="fc30d-119">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
