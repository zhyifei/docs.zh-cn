---
title: Windows 窗体应用程序基础知识
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349162"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Windows 窗体应用程序基础知识 (Visual Basic)

An important part of Visual Basic is the ability to create Windows Forms applications that run locally on users' computers. You can use Visual Studio to create the application and user interface using Windows Forms. A Windows Forms application is built on classes from the <xref:System.Windows.Forms> namespace.

## <a name="designing-windows-forms-applications"></a>Designing Windows Forms Applications

You can create Windows Forms and Windows service applications with Visual Studio. 有关更多信息，请参见下列主题：

- [Getting Started with Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Provides information on how to create and program Windows Forms.

- [Windows Forms Controls](../../../framework/winforms/controls/index.md). Collection of topics detailing the use of Windows Forms controls.

- [Windows Service Applications](../../../framework/windows-services/index.md). Lists topics that explain how to create Windows services.

## <a name="building-rich-interactive-user-interfaces"></a>构建丰富的交互式用户界面

Windows Forms is the smart-client component of the .NET Framework, a set of managed libraries that enable common application tasks such as reading and writing to the file system. Using a development environment like Visual Studio, you can create Windows Forms applications that display information, request input from users, and communicate with remote computers over a network.

In Windows Forms, a form is a visual surface on which you display information to the user. You commonly build Windows Forms applications by placing controls on forms and developing responses to user actions, such as mouse clicks or key presses. 控件是离散的用户界面 (UI) 元素，用于显示数据或接受数据输入。

### <a name="events"></a>事件

When a user does something to your form or one of its controls, it generates an event. 你的应用程序通过使用代码对这些事件做出反应，并在事件发生时对其进行处理。 有关详细信息，请参阅[在 Windows 窗体中创建事件处理程序](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)。

### <a name="controls"></a>控件

Windows Forms contains a variety of controls that you can place on forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even Web pages. 有关可在窗体上使用的所有控件的列表，请参阅[在 Windows 窗体上使用的控件](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md)。 如果某个现有控件不满足你的需要，Windows 窗体还支持使用 <xref:System.Windows.Forms.UserControl> 类创建自己的自定义控件。

Windows 窗体具有丰富的 UI 控件，这些控件可模拟 Microsoft Office 等高端应用程序中的功能。 Using the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> control, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.

With the Visual Studio drag-and-drop forms designer, you can easily create Windows Forms applications: just select the controls with your cursor and place them where you want on the form. The designer provides tools such as grid lines and "snap lines" to take the hassle out of aligning controls. And whether you use Visual Studio or compile at the command line, you can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts with minimal time and effort.

### <a name="custom-ui-elements"></a>Custom UI Elements

Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains all of the classes you need to render lines, circles, and other shapes directly on a form.

For step-by-step information about using these features, see the following Help topics.

|功能|查看|
|--------|---------|
|Create a new Windows Forms application with Visual Studio|[Tutorial 1: Create a picture viewer](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Use controls on forms|[如何：向 Windows 窗体添加控件](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Create graphics with <xref:System.Drawing>|[图形编程入门](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Create custom controls|[如何：从 UserControl 类继承](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>显示和操作数据

许多应用程序必须显示数据库、XML 文件、XML Web 服务或其他数据源中的数据。 Windows Forms provides a flexible control called the <xref:System.Windows.Forms.DataGridView> control for rendering such tabular data in a traditional row and column format, so that every piece of data occupies its own cell. Using <xref:System.Windows.Forms.DataGridView> you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.

通过网络连接到数据源对于 Windows 窗体智能客户端而言是一个简单的任务。 The <xref:System.Windows.Forms.BindingSource> component, new with Windows Forms in Visual Studio 2005 and the .NET Framework 2.0, represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source. <xref:System.Windows.Forms.BindingNavigator> 控件通过 <xref:System.Windows.Forms.BindingSource> 组件提供一个简单界面，可供用户在记录间导航。

### <a name="data-bound-controls"></a>Data-Bound Controls

You can create data-bound controls easily using the Data Sources window, which displays data sources such as databases, Web services, and objects in your project. 可以通过将此窗口中的项拖动到项目中的窗体上来创建数据绑定控件。 还可以通过将对象从“数据源”窗口拖动到现有控件上来将现有控件与数据进行数据绑定。

### <a name="settings"></a>设置

Another type of data binding you can manage in Windows Forms is settings. Most smart-client applications must retain some information about their run-time state, such as the last-known size of forms, and retain user-preference data, such as default locations for saved files. The application-settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer. Once defined using either Visual Studio or a code editor, these settings are persisted as XML and automatically read back into memory at run time.

For step-by-step information about using these features, see the following Help topics.

|功能|查看|
|--------|---------|
|Use the <xref:System.Windows.Forms.BindingSource> component|[如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Work with ADO.NET data sources|[如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Use the Data Sources window|[演练：在 Windows 窗体上显示数据](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>将应用程序部署到客户端计算机

Once you have written your application, you must send it to your users so that they can install and run it on their own client computers. Using the ClickOnce technology, you can deploy your applications from within Visual Studio by using just a few clicks and provide users with a URL pointing to your application on the Web. ClickOnce manages all of the elements and dependencies in your application and ensures that the application is properly installed on the client computer.

ClickOnce applications can be configured to run only when the user is connected to the network, or to run both online and offline. When you specify that an application should support offline operation, ClickOnce adds a link to your application in the user's **Start** menu, so that the user can open it without using the URL.

更新应用程序时，便向你的 Web 服务器发布了一个新的部署清单和应用程序的一个新副本。 ClickOnce detects that there is an update available and upgrades the user's installation; no custom programming is required to update old assemblies.

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about using these features, see the following Help topics:

|功能|查看|
|--------|---------|
|Deploy an application with ClickOnce|[如何：使用发布向导发布 ClickOnce 应用程序](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [演练：手动部署 ClickOnce 应用程序](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Update a ClickOnce deployment|[如何：管理 ClickOnce 应用程序的更新](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Manage security with ClickOnce|[如何：启用 ClickOnce 安全设置](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>其他控件和功能

Windows 窗体中有许多其他功能，可帮助快速轻松地实现常见任务，如对创建对话框、打印、添加帮助和文档以及将应用程序本地化为多种语言的支持。 In addition, Windows Forms relies on the robust security system of the .NET Framework, enabling you to release more secure applications to your customers.

For step-by-step information about using these features, see the following Help topics:

|功能|查看|
|--------|---------|
|Print the contents of a form|[如何：在 Windows 窗体中打印图形](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [如何：打印 Windows 窗体中的多页文本文件](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|了解有关 Windows 窗体安全的详细信息|[Windows 窗体中的安全性概述](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Windows 窗体概述](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms 对象](../../../visual-basic/language-reference/objects/my-forms-object.md)
