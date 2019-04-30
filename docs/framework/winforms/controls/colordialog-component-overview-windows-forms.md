---
title: ColorDialog 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 284d42218fb4fbce873325b1e45c883d51eefab8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956333"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="e38f5-102">ColorDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="e38f5-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e38f5-103">Windows 窗体<xref:System.Windows.Forms.ColorDialog>组件是一个预配置的对话框，允许用户从调色板选择颜色以及将自定义颜色添加到该调色板。</span><span class="sxs-lookup"><span data-stu-id="e38f5-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="e38f5-104">此对话框与在其他基于 Windows 的应用程序中看到的用于选择颜色的对话框相同。</span><span class="sxs-lookup"><span data-stu-id="e38f5-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="e38f5-105">在基于 Windows 的应用程序中，使用它作为一种替代配置自己对话框的简单解决方案。</span><span class="sxs-lookup"><span data-stu-id="e38f5-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="e38f5-106">中返回在对话框中选择的颜色<xref:System.Windows.Forms.ColorDialog.Color%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e38f5-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="e38f5-107">如果<xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>属性设置为`false`、"自定义颜色"按钮处于禁用状态，并且用户仅限于调色板中的预定义颜色。</span><span class="sxs-lookup"><span data-stu-id="e38f5-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="e38f5-108">如果<xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>属性设置为`true`，用户不能选择抖色的颜色。</span><span class="sxs-lookup"><span data-stu-id="e38f5-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="e38f5-109">若要显示对话框中，必须调用其<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e38f5-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e38f5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e38f5-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="e38f5-111">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="e38f5-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="e38f5-112">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="e38f5-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="e38f5-113">如何：更改 Windows 窗体 ColorDialog 组件的外观</span><span class="sxs-lookup"><span data-stu-id="e38f5-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
