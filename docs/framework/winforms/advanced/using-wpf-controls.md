---
title: 使用 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197465"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="ca675-102">在 Windows 窗体应用中使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="ca675-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="ca675-103">您可以在基于 Windows 窗体的应用程序中使用 Windows Presentation Foundation （WPF）控件。</span><span class="sxs-lookup"><span data-stu-id="ca675-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="ca675-104">尽管这是两种不同的视图技术，但它们可以顺畅地互操作。</span><span class="sxs-lookup"><span data-stu-id="ca675-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="ca675-105">Visual Studio 中的 Windows 窗体设计器提供了用于承载 Windows Presentation Foundation 控件的可视化设计环境。</span><span class="sxs-lookup"><span data-stu-id="ca675-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="ca675-106">WPF 控件由名为 <xref:System.Windows.Forms.Integration.ElementHost>的特殊 Windows 窗体控件承载。</span><span class="sxs-lookup"><span data-stu-id="ca675-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="ca675-107">此控件允许 WPF 控件参与窗体的布局以及接收键盘和鼠标消息。</span><span class="sxs-lookup"><span data-stu-id="ca675-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="ca675-108">在设计时，您可以像对任何 Windows 窗体控件一样排列 <xref:System.Windows.Forms.Integration.ElementHost> 控件。</span><span class="sxs-lookup"><span data-stu-id="ca675-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="ca675-109">你还可以在基于 WPF 的应用程序中使用 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ca675-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="ca675-110">有关详细信息，请参阅[在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="ca675-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca675-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca675-111">See also</span></span>

- [<span data-ttu-id="ca675-112">WPF 和 Windows 窗体互操作</span><span class="sxs-lookup"><span data-stu-id="ca675-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
