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
# <a name="helpprovider-component-overview-windows-forms"></a>HelpProvider 组件概述（Windows 窗体）
Windows 窗体[HelpProvider](../../../../docs/framework/winforms/controls/helpprovider-component-windows-forms.md)组件用于将 HTML Help 1.x 帮助文件 （HTML Help Workshop 生成的.chm 文件或.htm 文件） 与 Windows 应用程序相关联。 你可以提供各种不同的方式的帮助：  
  
-   为 Windows 窗体上的控件提供区分上下文的帮助。  
  
-   提供有关特定的对话框中或在对话框上的特定控件的上下文相关帮助。  
  
-   打开到特定区域，如的主页链接的目录、 索引或搜索函数的帮助文件。  
  
## <a name="using-the-help-provider"></a>使用帮助提供程序  
 添加<xref:System.Windows.Forms.HelpProvider>向 Windows 窗体组件允许要公开的帮助属性的窗体上的其他控件<xref:System.Windows.Forms.HelpProvider>组件。 这使你可以提供用于在 Windows 窗体上控件的帮助。 你可以将关联的帮助文件<xref:System.Windows.Forms.HelpProvider>组件使用<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性。 指定通过调用提供的帮助类型<xref:System.Windows.Forms.HelpProvider.SetHelpNavigator%2A>并提供一个介于<xref:System.Windows.Forms.HelpNavigator>枚举为指定的控件。 你提供的关键字或主题的帮助通过调用<xref:System.Windows.Forms.HelpProvider.SetHelpKeyword%2A>方法。  
  
 （可选） 若要将特定的帮助字符串与另一个控件相关联，使用<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>方法。 当用户按下 F1 键，而在控件有焦点，您将使用此方法的控件相关联的字符串显示在弹出窗口。  
  
 如果<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>尚未设置，必须使用<xref:System.Windows.Forms.HelpProvider.SetHelpString%2A>提供帮助文本。 如果同时设置了<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>和的帮助字符串中，帮助基于<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>将优先。  
  
> [!NOTE]
>  你可能会遇到问题使用相对路径时指定的帮助文件的路径中<xref:System.Windows.Forms.Help.ShowHelp%2A>方法或<xref:System.Windows.Forms.HelpProvider.HelpNamespace%2A>属性<xref:System.Windows.Forms.HelpProvider>控件。 在这种情况下，一定要使用的绝对文件路径指定的帮助文件。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体应用程序中的帮助系统](../../../../docs/framework/winforms/advanced/help-systems-in-windows-forms-applications.md)
