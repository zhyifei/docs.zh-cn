---
title: 在 Windows 窗体中集成用户帮助
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: b16ba14eea68083cd7bdfc91c88375406137f450
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527218"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="cac28-102">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="cac28-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="cac28-103">生成基于 Windows 的应用程序的一个必要的但经常被忽略，方面是帮助系统中，因为这是用户转混淆次协助的地方。</span><span class="sxs-lookup"><span data-stu-id="cac28-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="cac28-104">Windows 窗体支持两种不同类型的帮助，每个提供的[HelpProvider 组件](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="cac28-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="cac28-105">第一个涉及用户指向的 HTML 或 HTML 帮助 1 的帮助文件。*x*或更高版本格式。</span><span class="sxs-lookup"><span data-stu-id="cac28-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="cac28-106">第二个可以显示简要的"这是什么"-键入单独的控件; 上的帮助这是在对话框上特别有用。</span><span class="sxs-lookup"><span data-stu-id="cac28-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="cac28-107">可以在同一个窗体上使用两种类型的帮助。</span><span class="sxs-lookup"><span data-stu-id="cac28-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="cac28-108">此外， [ToolTip 组件](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)可以用于为 Windows 窗体上的控件提供单独的帮助。</span><span class="sxs-lookup"><span data-stu-id="cac28-108">Additionally, the [ToolTip Component](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cac28-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="cac28-109">In This Section</span></span>  
 [<span data-ttu-id="cac28-110">如何：在 Windows 应用程序中提供帮助</span><span class="sxs-lookup"><span data-stu-id="cac28-110">How to: Provide Help in a Windows Application</span></span>](../../../../docs/framework/winforms/advanced/how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="cac28-111">说明如何使用`HelpProvider`组件将控件链接到文件，帮助系统中。</span><span class="sxs-lookup"><span data-stu-id="cac28-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="cac28-112">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="cac28-112">How to: Display Pop-up Help</span></span>](../../../../docs/framework/winforms/advanced/how-to-display-pop-up-help.md)  
 <span data-ttu-id="cac28-113">说明如何使用`HelpProvider`组件要在 Windows 窗体上显示弹出帮助。</span><span class="sxs-lookup"><span data-stu-id="cac28-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="cac28-114">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="cac28-114">Control Help Using ToolTips</span></span>](../../../../docs/framework/winforms/advanced/control-help-using-tooltips.md)  
 <span data-ttu-id="cac28-115">描述如何使用`ToolTip`组件显示特定于控件的帮助。</span><span class="sxs-lookup"><span data-stu-id="cac28-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cac28-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="cac28-116">Related Sections</span></span>  
 [<span data-ttu-id="cac28-117">HelpProvider 组件</span><span class="sxs-lookup"><span data-stu-id="cac28-117">HelpProvider Component</span></span>](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="cac28-118">说明的基础知识`HelpProvider`组件。</span><span class="sxs-lookup"><span data-stu-id="cac28-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="cac28-119">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="cac28-119">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="cac28-120">说明的基础知识`ToolTip`组件。</span><span class="sxs-lookup"><span data-stu-id="cac28-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="cac28-121">Windows 窗体概述</span><span class="sxs-lookup"><span data-stu-id="cac28-121">Windows Forms Overview</span></span>](../../../../docs/framework/winforms/windows-forms-overview.md)  
 <span data-ttu-id="cac28-122">介绍 Windows 窗体的基础知识。</span><span class="sxs-lookup"><span data-stu-id="cac28-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="cac28-123">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="cac28-123">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)  
 <span data-ttu-id="cac28-124">提供 Windows 窗体的概述。</span><span class="sxs-lookup"><span data-stu-id="cac28-124">Provides an overview of Windows Forms.</span></span>
