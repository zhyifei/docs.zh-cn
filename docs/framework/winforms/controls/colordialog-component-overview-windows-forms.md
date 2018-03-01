---
title: "ColorDialog 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5df0d7ddd16de5bd8bb052c09731df6583ca4903
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="cf580-102">ColorDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="cf580-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="cf580-103">Windows 窗体<xref:System.Windows.Forms.ColorDialog>组件是预配置的对话框，它允许用户选择一种颜色的调色板并向此调色板添加自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="cf580-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="cf580-104">此对话框与在其他基于 Windows 的应用程序中看到的用于选择颜色的对话框相同。</span><span class="sxs-lookup"><span data-stu-id="cf580-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="cf580-105">在基于 Windows 的应用程序中，使用它作为一种替代配置自己对话框的简单解决方案。</span><span class="sxs-lookup"><span data-stu-id="cf580-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="cf580-106">在中返回在对话框中选定的颜色<xref:System.Windows.Forms.ColorDialog.Color%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="cf580-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="cf580-107">如果<xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>属性设置为`false`、"自定义颜色"按钮处于禁用状态和用户仅限于调色板中的预定义颜色。</span><span class="sxs-lookup"><span data-stu-id="cf580-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="cf580-108">如果<xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>属性设置为`true`，用户无法选择抖色的颜色。</span><span class="sxs-lookup"><span data-stu-id="cf580-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="cf580-109">若要显示对话框中，必须调用其<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="cf580-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf580-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf580-110">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="cf580-111">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="cf580-111">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="cf580-112">对话框控件和组件</span><span class="sxs-lookup"><span data-stu-id="cf580-112">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [<span data-ttu-id="cf580-113">如何：更改 Windows 窗体 ColorDialog 组件的外观</span><span class="sxs-lookup"><span data-stu-id="cf580-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
