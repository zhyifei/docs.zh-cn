---
title: 如何：更改 Windows 窗体 ColorDialog 组件的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: d2bb9e06d9d84a9b61c67510e9c012066f69d55e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59329227"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="1100f-102">如何：更改 Windows 窗体 ColorDialog 组件的外观</span><span class="sxs-lookup"><span data-stu-id="1100f-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="1100f-103">你可以配置 Windows 窗体外观<xref:System.Windows.Forms.ColorDialog>组件与多个其属性。</span><span class="sxs-lookup"><span data-stu-id="1100f-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="1100f-104">该对话框具有两个部分 — 一个显示基本颜色，另一部分允许用户定义的自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="1100f-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="1100f-105">大部分属性限制哪些用户可以从对话框中选择的颜色。</span><span class="sxs-lookup"><span data-stu-id="1100f-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="1100f-106">如果<xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>属性设置为`true`，允许用户定义自定义颜色。</span><span class="sxs-lookup"><span data-stu-id="1100f-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="1100f-107"><xref:System.Windows.Forms.ColorDialog.FullOpen%2A>属性是`true`如果对话框中展开定义自定义颜色; 通过否则用户必须单击"定义自定义颜色"按钮。</span><span class="sxs-lookup"><span data-stu-id="1100f-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="1100f-108">当<xref:System.Windows.Forms.ColorDialog.AnyColor%2A>属性设置为`true`，对话框显示基本颜色集中可用的所有颜色。</span><span class="sxs-lookup"><span data-stu-id="1100f-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="1100f-109">如果<xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>属性设置为`true`，用户不能选择抖色的颜色; 仅纯色可供选择。</span><span class="sxs-lookup"><span data-stu-id="1100f-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="1100f-110">如果<xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>属性设置为`true`，帮助按钮显示在对话框中。</span><span class="sxs-lookup"><span data-stu-id="1100f-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="1100f-111">当用户单击帮助按钮<xref:System.Windows.Forms.ColorDialog>组件的<xref:System.Windows.Forms.CommonDialog.HelpRequest>引发事件。</span><span class="sxs-lookup"><span data-stu-id="1100f-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="1100f-112">若要配置的颜色对话框外观</span><span class="sxs-lookup"><span data-stu-id="1100f-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="1100f-113">设置<xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>， <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>， <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>，和<xref:System.Windows.Forms.ColorDialog.ShowHelp%2A>属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="1100f-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1100f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1100f-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="1100f-115">ColorDialog 组件</span><span class="sxs-lookup"><span data-stu-id="1100f-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="1100f-116">ColorDialog 组件概述</span><span class="sxs-lookup"><span data-stu-id="1100f-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
