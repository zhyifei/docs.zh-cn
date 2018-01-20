---
title: "Windows 窗体应用程序基础知识 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7872d3c7b19ec9cd7059cccf41e5fab50d85123b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="windows-forms-application-basics-visual-basic"></a>Windows 窗体应用程序基础知识 (Visual Basic)
一个重要部分[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]是创建 Windows 窗体应用程序在用户的计算机上本地运行的能力。 Visual Studio 可用于创建使用 Windows 窗体的应用程序和用户界面。 Windows 窗体应用程序基于从类<xref:System.Windows.Forms>命名空间。  
  
## <a name="designing-windows-forms-applications"></a>设计 Windows 窗体应用程序  
 你可以创建 Windows 窗体和 Windows 服务应用程序与[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]。 有关详细信息，请参阅下列主题：  
  
-   [Windows 窗体入门](../../../framework/winforms/getting-started-with-windows-forms.md)。 提供有关如何创建和程序 Windows 窗体的信息。  
   
-   [Windows 窗体控件](../../../framework/winforms/controls/index.md)。 主题详细说明使用 Windows 窗体控件的集合。  
  
-   [Windows 服务应用程序](../../../framework/windows-services/index.md)。 说明如何创建 Windows 服务的主题列表。  
  
## <a name="building-rich-interactive-user-interfaces"></a>构建丰富的交互式用户界面  
 Windows 窗体是的智能客户端组件[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，一组的托管库，使读取和写入文件系统等常见应用程序任务。 使用类似的开发环境[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]，你可以通过网络与远程计算机创建 Windows 窗体应用程序显示的信息、 请求来自用户的输入和沟通。  
  
 在 Windows 窗体，窗体是向用户的信息显示在其一个可视化图面。 通常情况下，通过将窗体上的控件和开发对用户操作，如点击鼠标或按键响应需要构建 Windows 窗体应用程序。 控件是离散的用户界面 (UI) 元素，用于显示数据或接受数据输入。  
  
### <a name="events"></a>事件  
 当用户执行某些内容到你的窗体或其某个控件时，它会生成一个事件。 你的应用程序通过使用代码对这些事件做出反应，并在事件发生时对其进行处理。 有关详细信息，请参阅[在 Windows 窗体中创建事件处理程序](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)。  
  
### <a name="controls"></a>控件  
 Windows 窗体包含各种可以将它们放置在窗体的控件： 显示文本框、 按钮、 下拉框、 单选按钮和甚至网页的控件。 有关可在窗体上使用的所有控件的列表，请参阅[在 Windows 窗体上使用的控件](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md)。 如果某个现有控件不满足你的需要，Windows 窗体还支持使用 <xref:System.Windows.Forms.UserControl> 类创建自己的自定义控件。  
  
 Windows 窗体具有丰富的 UI 控件，这些控件可模拟 Microsoft Office 等高端应用程序中的功能。 使用<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.MenuStrip>控件，可以创建包含文本和图像、 显示子菜单和托管其他控件，如文本框和组合框的工具栏和菜单。  
  
 与[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]拖放窗体设计器中，可以轻松创建 Windows 窗体应用程序： 只需用光标选中控件并将它们放置在要在窗体上。 设计器提供诸如网格线和"对齐线"等工具可简化对齐控件。 无论是使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]或编译命令行中，你可以使用<xref:System.Windows.Forms.FlowLayoutPanel>，<xref:System.Windows.Forms.TableLayoutPanel>和<xref:System.Windows.Forms.SplitContainer>控件，创建高级窗体布局的最小时间和精力。  
  
### <a name="custom-ui-elements"></a>自定义 UI 元素  
 最后，如果必须创建自己的自定义用户界面元素，<xref:System.Drawing>命名空间包含的所有类需要呈现线条、 圆形和其他形状直接在窗体上的。  
  
 有关使用这些功能的分步信息，请参阅下列帮助主题。  
  
|到|查看|  
|--------|---------|  
|创建与新的 Windows 窗体应用程序[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]|[演练： 创建简单的 Windows 窗体](http://msdn.microsoft.com/library/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|使用窗体上控件|[如何：向 Windows 窗体添加控件](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|创建与图形<xref:System.Drawing>|[图形编程入门](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|创建自定义控件|[如何：从 UserControl 类继承](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>显示和操作数据  
 许多应用程序必须显示数据库、XML 文件、XML Web 服务或其他数据源中的数据。 Windows 窗体提供了一个灵活的控件，调用<xref:System.Windows.Forms.DataGridView>呈现在传统的行和列的格式，此类表格数据，以便每个数据块占据其自己的单元格的控件。 使用<xref:System.Windows.Forms.DataGridView>你可以自定义各个单元格的外观、 锁定的位置，在任意行和列和其他功能单元格内部显示复杂控件。  
  
 通过网络连接到数据源对于 Windows 窗体智能客户端而言是一个简单的任务。 <xref:System.Windows.Forms.BindingSource> 组件（对于 [!INCLUDE[vsprvslong](~/includes/vsprvslong-md.md)] 和 [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] 中的 Windows 窗体而言是全新内容）表示与数据源的连接，公开将数据绑定到控件的方法，导航到上一个和下一个记录，编辑记录并且将更改保存到原始源。 <xref:System.Windows.Forms.BindingNavigator> 控件通过 <xref:System.Windows.Forms.BindingSource> 组件提供一个简单界面，可供用户在记录间导航。  
  
### <a name="data-bound-controls"></a>数据绑定控件  
 你可以创建数据绑定控件轻松使用数据源窗口中，你的项目中显示数据源，如数据库、 Web 服务和对象。 可以通过将此窗口中的项拖动到项目中的窗体上来创建数据绑定控件。 还可以通过将对象从“数据源”窗口拖动到现有控件上来将现有控件与数据进行数据绑定。  
  
### <a name="settings"></a>设置  
 你可以管理 Windows 窗体中的数据绑定的另一种是设置。 大多数智能客户端应用程序必须保留有关其运行时状态，例如窗体，最后一次大小的一些信息，并保留用户首选项数据，如保存文件的默认位置。 应用程序设置功能通过提供一种简单的方法将这两种类型的设置存储客户端计算机上满足这些要求。 一次定义使用[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]或代码编辑器中，这些设置便作为 XML 保留并自动在运行时读取回内存。  
  
 有关使用这些功能的分步信息，请参阅下列帮助主题。  
  
|到|查看|  
|--------|---------|  
|使用<xref:System.Windows.Forms.BindingSource>组件|[如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|使用[!INCLUDE[vstecado](~/includes/vstecado-md.md)]数据源|[如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|使用数据源窗口|[演练：在 Windows 窗体上显示数据](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>将应用程序部署到客户端计算机  
 写入你的应用程序之后，以便他们可以安装和运行在其自己的客户端计算机上必须将它发送到你的用户。 使用[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]技术，你可以部署你的应用程序从内[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]，只需几次点击并为用户提供指向 Web 上的应用程序的 URL。 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]管理的所有元素和你的应用程序中的依赖关系，并确保客户端计算机上正确安装应用程序。  
  
 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 应用程序可以配置为仅在用户连接到网络时运行，或配置为联机和脱机时均可运行。 指定应用程序应支持脱机操作时[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]将链接添加到你的应用程序在用户的**启动**菜单上，以便用户可以打开它而使用的 URL。  
  
 更新应用程序时，便向你的 Web 服务器发布了一个新的部署清单和应用程序的一个新副本。 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]检测到存在可用的更新和升级用户的安装;无需任何自定义编程需要更新旧程序集。  
  
 有关 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] 的完整介绍，请参阅 [ClickOnce 安全和部署](/visualstudio/deployment/clickonce-security-and-deployment)。 有关使用这些功能的分步信息，请参阅下列帮助主题：  
  
|到|查看|  
|--------|---------|  
|部署的应用程序[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[如何：使用发布向导发布 ClickOnce 应用程序](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [演练：手动部署 ClickOnce 应用程序](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|更新[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]部署|[如何：管理 ClickOnce 应用程序的更新](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|管理与安全性[!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[如何：启用 ClickOnce 安全设置](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>其他控件和功能  
 Windows 窗体中有许多其他功能，可帮助快速轻松地实现常见任务，如对创建对话框、打印、添加帮助和文档以及将应用程序本地化为多种语言的支持。 此外，Windows 窗体依赖于可靠的安全系统[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，使你能够更安全应用程序发布到你的客户。  
  
 有关使用这些功能的分步信息，请参阅下列帮助主题：  
  
|到|查看|  
|--------|---------|  
|打印窗体的内容|[如何：在 Windows 窗体中打印图形](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [如何：打印 Windows 窗体中的多页文本文件](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|了解有关 Windows 窗体安全的详细信息|[Windows 窗体中的安全性概述](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>  
 [Windows 窗体概述](../../../framework/winforms/windows-forms-overview.md)  
 [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)
