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
ms.openlocfilehash: 207ceeafa2ea06340310577c636deb5ea1977aae
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715303"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="2c422-102">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="2c422-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="2c422-103">构建基于 Windows 的应用程序的一个很必要，但经常被忽略的方面是帮助系统时，因为这是用户在其中打开有关混淆的时间中的帮助。</span><span class="sxs-lookup"><span data-stu-id="2c422-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="2c422-104">Windows 窗体支持两种不同类型的帮助，每个提供的[HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="2c422-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="2c422-105">第一个涉及用户指向帮助文件的 HTML 或 HTML 帮助 1。*x*或更高版本格式。</span><span class="sxs-lookup"><span data-stu-id="2c422-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="2c422-106">第二个可以显示简短的"这是什么"-键入单个控件; 上的帮助这是在对话框中特别有用。</span><span class="sxs-lookup"><span data-stu-id="2c422-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="2c422-107">可以在同一个窗体上使用两种类型的帮助。</span><span class="sxs-lookup"><span data-stu-id="2c422-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="2c422-108">此外， [ToolTip 组件](../controls/tooltip-component-windows-forms.md)可用于为 Windows 窗体上控件提供单独的帮助。</span><span class="sxs-lookup"><span data-stu-id="2c422-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c422-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="2c422-109">In This Section</span></span>  
 [<span data-ttu-id="2c422-110">如何：在 Windows 应用程序中提供帮助</span><span class="sxs-lookup"><span data-stu-id="2c422-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="2c422-111">说明如何使用`HelpProvider`组件将控件链接到文件，帮助系统中。</span><span class="sxs-lookup"><span data-stu-id="2c422-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="2c422-112">如何：显示弹出帮助</span><span class="sxs-lookup"><span data-stu-id="2c422-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="2c422-113">说明如何使用`HelpProvider`组件在 Windows 窗体上显示弹出帮助。</span><span class="sxs-lookup"><span data-stu-id="2c422-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="2c422-114">使用工具提示的控件帮助</span><span class="sxs-lookup"><span data-stu-id="2c422-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="2c422-115">介绍了如何使用`ToolTip`组件显示特定于控件的帮助。</span><span class="sxs-lookup"><span data-stu-id="2c422-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2c422-116">相关章节</span><span class="sxs-lookup"><span data-stu-id="2c422-116">Related Sections</span></span>  
 [<span data-ttu-id="2c422-117">HelpProvider 组件</span><span class="sxs-lookup"><span data-stu-id="2c422-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="2c422-118">说明的基础知识`HelpProvider`组件。</span><span class="sxs-lookup"><span data-stu-id="2c422-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="2c422-119">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="2c422-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="2c422-120">说明的基础知识`ToolTip`组件。</span><span class="sxs-lookup"><span data-stu-id="2c422-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="2c422-121">Windows 窗体概述</span><span class="sxs-lookup"><span data-stu-id="2c422-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="2c422-122">介绍 Windows 窗体的基础知识。</span><span class="sxs-lookup"><span data-stu-id="2c422-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="2c422-123">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="2c422-123">Windows Forms</span></span>](../index.md)  
 <span data-ttu-id="2c422-124">概述 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="2c422-124">Provides an overview of Windows Forms.</span></span>
