---
title: "ToolBar 控件（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 204c4229852d4e91d2af7a27163c7418b9a1e9b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="toolbar-control-windows-forms"></a><span data-ttu-id="5025a-102">ToolBar 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="5025a-102">ToolBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="5025a-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 `ToolBar` 控件并添加了功能；但是，可以选择保留 `ToolBar` 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="5025a-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the `ToolBar` control; however, the `ToolBar` control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="5025a-104">Windows 窗体 `ToolBar` 控件在窗体上用作可显示下拉菜单的行的控件条以及可激活命令的位图按钮。</span><span class="sxs-lookup"><span data-stu-id="5025a-104">The Windows Forms `ToolBar` control is used on forms as a control bar that displays a row of drop-down menus and bitmapped buttons that activate commands.</span></span> <span data-ttu-id="5025a-105">因此，单击工具栏按钮相当于选择菜单命令。</span><span class="sxs-lookup"><span data-stu-id="5025a-105">Thus, clicking a toolbar button is equivalent to choosing a menu command.</span></span> <span data-ttu-id="5025a-106">按钮可配置为显示为并用作下压按钮、下拉菜单或分隔符。</span><span class="sxs-lookup"><span data-stu-id="5025a-106">The buttons can be configured to appear and behave as push buttons, drop-down menus, or separators.</span></span> <span data-ttu-id="5025a-107">通常，工具栏包含对应于应用程序菜单结构中的项的按钮和菜单，提供对应用程序最常用的函数和命令的快速访问。</span><span class="sxs-lookup"><span data-stu-id="5025a-107">Typically, a toolbar contains buttons and menus that correspond to items in an application's menu structure, providing quick access to an application's most frequently used functions and commands.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5025a-108">`ToolBar` 控件的 <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> 属性将 <xref:System.Windows.Forms.ContextMenu> 类的实例作为引用。</span><span class="sxs-lookup"><span data-stu-id="5025a-108">The `ToolBar` control's <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> property takes an instance of the <xref:System.Windows.Forms.ContextMenu> class as a reference.</span></span> <span data-ttu-id="5025a-109">在应用程序的工具栏上实现此类按钮时，请仔细考虑所传递的引用，因为此属性将接受从 <xref:System.Windows.Forms.Menu> 类继承的所有对象。</span><span class="sxs-lookup"><span data-stu-id="5025a-109">Carefully consider the reference you pass when implementing this sort of button on toolbars in your application, as the property will accept any object that inherits from the <xref:System.Windows.Forms.Menu> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5025a-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="5025a-110">In This Section</span></span>  
 [<span data-ttu-id="5025a-111">ToolBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="5025a-111">ToolBar Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 <span data-ttu-id="5025a-112">介绍 `ToolBar` 控件的一般概念，此控件可用于设计用户可使用的自定义工具栏。</span><span class="sxs-lookup"><span data-stu-id="5025a-112">Introduces the general concepts of the `ToolBar` control, which allows you to design custom toolbars that your users can work with.</span></span>  
  
 [<span data-ttu-id="5025a-113">如何：向 ToolBar 控件添加按钮</span><span class="sxs-lookup"><span data-stu-id="5025a-113">How to: Add Buttons to a ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 <span data-ttu-id="5025a-114">介绍如何向 `ToolBar` 控件添加按钮。</span><span class="sxs-lookup"><span data-stu-id="5025a-114">Describes how to add buttons to a `ToolBar` control.</span></span>  
  
 [<span data-ttu-id="5025a-115">如何：定义 ToolBar 控件按钮的图标</span><span class="sxs-lookup"><span data-stu-id="5025a-115">How to: Define an Icon for a ToolBar Button</span></span>](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 <span data-ttu-id="5025a-116">介绍如何显示 `ToolBar` 控件按钮中的图标。</span><span class="sxs-lookup"><span data-stu-id="5025a-116">Describes how to display icons within a `ToolBar` control's buttons.</span></span>  
  
 [<span data-ttu-id="5025a-117">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="5025a-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 <span data-ttu-id="5025a-118">指示如何编写代码以解释用户在 `ToolBar` 控件中单击的按钮。</span><span class="sxs-lookup"><span data-stu-id="5025a-118">Gives directions on writing code to interpret which button the user clicks in a `ToolBar` control.</span></span>  
  
 <span data-ttu-id="5025a-119">另请参阅[如何： 定义工具栏按钮使用的设计器的图标](http://msdn.microsoft.com/library/ms233659\(v=vs.110\))，[如何： 将按钮添加到工具栏控件使用的设计器](http://msdn.microsoft.com/library/ms233650\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="5025a-119">Also see [How to: Define an Icon for a ToolBar Button Using the Designer](http://msdn.microsoft.com/library/ms233659\(v=vs.110\)), [How to: Add Buttons to a ToolBar Control Using the Designer](http://msdn.microsoft.com/library/ms233650\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5025a-120">参考</span><span class="sxs-lookup"><span data-stu-id="5025a-120">Reference</span></span>  
 <span data-ttu-id="5025a-121"><xref:System.Windows.Forms.ToolBar> 类</span><span class="sxs-lookup"><span data-stu-id="5025a-121"><xref:System.Windows.Forms.ToolBar> class</span></span>  
 <span data-ttu-id="5025a-122">提供类及其成员的相关引用信息。</span><span class="sxs-lookup"><span data-stu-id="5025a-122">Provides reference information on the class and its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5025a-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="5025a-123">Related Sections</span></span>  
 [<span data-ttu-id="5025a-124">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="5025a-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="5025a-125">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="5025a-125">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>  
  
 [<span data-ttu-id="5025a-126">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="5025a-126">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 <span data-ttu-id="5025a-127">介绍可以承载 Windows 窗体应用程序中的菜单、控件和用户控件的工具栏。</span><span class="sxs-lookup"><span data-stu-id="5025a-127">Describes toolbars that can host menus, controls, and user controls in Windows Forms applications.</span></span>
