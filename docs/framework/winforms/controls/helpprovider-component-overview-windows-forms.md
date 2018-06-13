---
title: HelpProvider 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- HelpProvider
helpviewer_keywords:
- HelpProvider component [Windows Forms], about HelpProvider component
- Help [Windows Forms], adding to Windows applications
- F1 Help [Windows Forms], adding to Windows Forms
- dialog boxes [Windows Forms], context-sensitive Help
- Windows Forms, context-sensitive Help
ms.assetid: 6b10c2cc-c577-4cb5-9669-e37b33416af9
ms.openlocfilehash: 5ad74b862c09734f3490210cb6898945a3c787fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528614"
---
# <a name="helpprovider-component-overview-windows-forms"></a><span data-ttu-id="e53b0-102">HelpProvider 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="e53b0-102">HelpProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="e53b0-103">Windows 窗体[HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)组件用于将 HTML Help 1.x 帮助文件 （HTML Help Workshop 生成的.chm 文件或.htm 文件） 与 Windows 应用程序相关联。</span><span class="sxs-lookup"><span data-stu-id="e53b0-103">The Windows Forms [HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md) component is used to associate an HTML Help 1.x Help file (either a .chm file, produced with the HTML Help Workshop, or an .htm file) with your Windows application.</span></span> <span data-ttu-id="e53b0-104">你可以提供各种不同的方式的帮助：</span><span class="sxs-lookup"><span data-stu-id="e53b0-104">You can provide help in a variety of ways:</span></span>  
  
-   <span data-ttu-id="e53b0-105">为 Windows 窗体上的控件提供区分上下文的帮助。</span><span class="sxs-lookup"><span data-stu-id="e53b0-105">Provide context-sensitive Help for controls on Windows Forms.</span></span>  
  
-   <span data-ttu-id="e53b0-106">提供有关特定的对话框中或在对话框上的特定控件的上下文相关帮助。</span><span class="sxs-lookup"><span data-stu-id="e53b0-106">Provide context-sensitive Help on a particular dialog box or specific controls on a dialog box.</span></span>  
  
-   <span data-ttu-id="e53b0-107">打开到特定区域，如的主页链接的目录、 索引或搜索函数的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="e53b0-107">Open a Help file to specific areas, such as the main page of a Table of Contents, the Index, or a search function.</span></span>  
  
## <a name="using-the-help-provider"></a><span data-ttu-id="e53b0-108">使用帮助提供程序</span><span class="sxs-lookup"><span data-stu-id="e53b0-108">Using the Help Provider</span></span>  
 <span data-ttu-id="e53b0-109">添加<xref:System.Windows.Forms.HelpProvider>向 Windows 窗体组件允许要公开的帮助属性的窗体上的其他控件<xref:System.Windows.Forms.HelpProvider>组件。</span><span class="sxs-lookup"><span data-stu-id="e53b0-109">Adding a <xref:System.Windows.Forms.HelpProvider> component to your Windows Form allows the other controls on the form to expose the Help properties of the <xref:System.Windows.Forms.HelpProvider> component.</span></span> <span data-ttu-id="e53b0-110">这使你可以提供用于在 Windows 窗体上控件的帮助。</span><span class="sxs-lookup"><span data-stu-id="e53b0-110">This enables you to provide help for the controls on your Windows Form.</span></span> <span data-ttu-id="e53b0-111">你可以将关联的帮助文件<xref:System.Windows.Forms.HelpProvider>组件使用<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e53b0-111">You can associate a Help file with the <xref:System.Windows.Forms.HelpProvider> component using the <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property.</span></span> <span data-ttu-id="e53b0-112">指定通过调用提供的帮助类型<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>并提供一个介于<xref:System.Windows.Forms.HelpNavigator>枚举为指定的控件。</span><span class="sxs-lookup"><span data-stu-id="e53b0-112">You specify the type of Help provided by calling <xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A> and providing a value from the <xref:System.Windows.Forms.HelpNavigator> enumeration for the specified control.</span></span> <span data-ttu-id="e53b0-113">你提供的关键字或主题的帮助通过调用<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e53b0-113">You provide the keyword or topic for Help by calling the <xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A> method.</span></span>  
  
 <span data-ttu-id="e53b0-114">（可选） 若要将特定的帮助字符串与另一个控件相关联，使用<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e53b0-114">Optionally, to associate a specific Help string with another control, use the <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> method.</span></span> <span data-ttu-id="e53b0-115">当用户按下 F1 键，而在控件有焦点，您将使用此方法的控件相关联的字符串显示在弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="e53b0-115">The string that you associate with a control using this method is displayed in a pop-up window when the user presses the F1 key while the control has focus.</span></span>  
  
 <span data-ttu-id="e53b0-116">如果<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>尚未设置，必须使用<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>提供帮助文本。</span><span class="sxs-lookup"><span data-stu-id="e53b0-116">If <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> has not been set, you must use <xref:System.Windows.Forms.HelpProvider.SetHelpString%2A> to provide the Help text.</span></span> <span data-ttu-id="e53b0-117">如果同时设置了<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>和的帮助字符串中，帮助基于<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>将优先。</span><span class="sxs-lookup"><span data-stu-id="e53b0-117">If you have set both <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> and the Help string, Help based on <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> will take precedence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e53b0-118">你可能会遇到问题使用相对路径时指定的帮助文件的路径中<xref:System.Windows.Forms.Help.ShowHelp%2A>方法或<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性<xref:System.Windows.Forms.HelpProvider>控件。</span><span class="sxs-lookup"><span data-stu-id="e53b0-118">You may encounter problems using the relative path when specifiying the path to the Help file in the <xref:System.Windows.Forms.Help.ShowHelp%2A> method or <xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A> property of the <xref:System.Windows.Forms.HelpProvider> control.</span></span> <span data-ttu-id="e53b0-119">在这种情况下，一定要使用的绝对文件路径指定的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="e53b0-119">As such, be sure to use the absolute file path to specify the Help file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e53b0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e53b0-120">See Also</span></span>  
 [<span data-ttu-id="e53b0-121">Windows 窗体应用程序中的帮助系统</span><span class="sxs-lookup"><span data-stu-id="e53b0-121">Help Systems in Windows Forms Applications</span></span>](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
