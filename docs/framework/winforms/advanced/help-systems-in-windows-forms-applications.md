---
title: Windows 窗体应用程序中的帮助系统
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], adding to Windows applications
- Windows applications [Windows Forms], providing Help systems
- What's This? Help
- Help [Windows Forms], Windows Forms
- HelpProvider component [Windows Forms], providing Help in Windows applications
ms.assetid: 2a96a278-432c-41fc-9e3c-5bfedf5e1267
ms.openlocfilehash: 1a02271d59a59f0a6e06a652a34922ba5dcdf1f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087263"
---
# <a name="help-systems-in-windows-forms-applications"></a><span data-ttu-id="c7718-102">Windows 窗体应用程序中的帮助系统</span><span class="sxs-lookup"><span data-stu-id="c7718-102">Help Systems in Windows Forms Applications</span></span>
<span data-ttu-id="c7718-103">其中一个最重要的礼物，如的应用程序，开发人员可以为用户提供的功能完善的帮助系统。</span><span class="sxs-lookup"><span data-stu-id="c7718-103">One of the most important courtesies you, as a developer of applications, can furnish your users with is a competent Help system.</span></span> <span data-ttu-id="c7718-104">这是他们将在这里打开时它们迷惑不解。</span><span class="sxs-lookup"><span data-stu-id="c7718-104">This is where they will turn when they become confused or disoriented.</span></span> <span data-ttu-id="c7718-105">提供在基于 Windows 的应用程序的帮助系统轻松可通过使用[HelpProvider 组件](../controls/helpprovider-component-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="c7718-105">Providing a Help system in a Windows-based application is easily done by using the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span>  
  
## <a name="different-types-of-help"></a><span data-ttu-id="c7718-106">不同类型的帮助</span><span class="sxs-lookup"><span data-stu-id="c7718-106">Different Types of Help</span></span>  
 <span data-ttu-id="c7718-107">Windows 窗体 <xref:System.Windows.Forms.HelpProvider> 组件用于将基于 Windows 的应用程序与 HTML Help 1.x 帮助文件（HTML Help Workshop 生成的 .chm 文件，或 .htm 文件）关联。</span><span class="sxs-lookup"><span data-stu-id="c7718-107">The Windows Forms <xref:System.Windows.Forms.HelpProvider> component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows-based application.</span></span> <span data-ttu-id="c7718-108"><xref:System.Windows.Forms.HelpProvider>组件可用于为 Windows 窗体上的控件或特定的控件提供上下文相关帮助。</span><span class="sxs-lookup"><span data-stu-id="c7718-108">The <xref:System.Windows.Forms.HelpProvider> component can be used to provide context-sensitive Help for controls on Windows Forms or specific controls.</span></span> <span data-ttu-id="c7718-109">此外，<xref:System.Windows.Forms.HelpProvider>组件可以打开帮助文件的特定区域，如表的内容、 索引或搜索功能的主页。</span><span class="sxs-lookup"><span data-stu-id="c7718-109">Additionally, the <xref:System.Windows.Forms.HelpProvider> component can open a Help file to specific areas, such as the main page of a table of contents, an index, or a search function.</span></span> <span data-ttu-id="c7718-110">有关常规信息<xref:System.Windows.Forms.HelpProvider>组件，请参阅[HelpProvider 组件概述](../controls/helpprovider-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="c7718-110">For general information about the <xref:System.Windows.Forms.HelpProvider> component, see [HelpProvider Component Overview](../controls/helpprovider-component-overview-windows-forms.md).</span></span> <span data-ttu-id="c7718-111">有关如何使用信息<xref:System.Windows.Forms.HelpProvider>组件在 Windows 窗体上显示弹出帮助，请参阅[如何：显示弹出帮助](how-to-display-pop-up-help.md)。</span><span class="sxs-lookup"><span data-stu-id="c7718-111">For information on how to use the <xref:System.Windows.Forms.HelpProvider> component to show pop-up Help on Windows Forms, see [How to: Display Pop-up Help](how-to-display-pop-up-help.md).</span></span> <span data-ttu-id="c7718-112">有关使用信息<xref:System.Windows.Forms.ToolTip>组件来显示特定于控件的帮助，请参阅[控制帮助使用工具提示](control-help-using-tooltips.md)。</span><span class="sxs-lookup"><span data-stu-id="c7718-112">For information on using the <xref:System.Windows.Forms.ToolTip> component to show control-specific Help, see [Control Help Using ToolTips](control-help-using-tooltips.md).</span></span>  
  
 <span data-ttu-id="c7718-113">你可以生成与 HTML Help Workshop HTML Help 1.x 文件。</span><span class="sxs-lookup"><span data-stu-id="c7718-113">You can generate HTML Help 1.x files with the HTML Help Workshop.</span></span> <span data-ttu-id="c7718-114">HTML 帮助的详细信息，请参阅"HTML Help Workshop"或在 MSDN 中的其他"HTML Help"主题。</span><span class="sxs-lookup"><span data-stu-id="c7718-114">For more information on HTML Help, see the "HTML Help Workshop" or the other "HTML Help" topics in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7718-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7718-115">See also</span></span>

- [<span data-ttu-id="c7718-116">在 Windows 窗体中集成用户帮助</span><span class="sxs-lookup"><span data-stu-id="c7718-116">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="c7718-117">HelpProvider 组件</span><span class="sxs-lookup"><span data-stu-id="c7718-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)
- [<span data-ttu-id="c7718-118">ToolTip 组件</span><span class="sxs-lookup"><span data-stu-id="c7718-118">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)
- [<span data-ttu-id="c7718-119">Windows 窗体概述</span><span class="sxs-lookup"><span data-stu-id="c7718-119">Windows Forms Overview</span></span>](../windows-forms-overview.md)
- [<span data-ttu-id="c7718-120">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c7718-120">Windows Forms</span></span>](../index.md)
