---
title: "如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 985aa58056f4c4ec8f3042c682291508f1434ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="0d69f-102">如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联</span><span class="sxs-lookup"><span data-stu-id="0d69f-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
>  <span data-ttu-id="0d69f-103">尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenuStrip>替换，并将功能添加到<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>的早期版本中，控件<xref:System.Windows.Forms.MainMenu>和<xref:System.Windows.Forms.ContextMenu>如果你选择将保留用于向后兼容性和将来使用。</span><span class="sxs-lookup"><span data-stu-id="0d69f-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="0d69f-104"><xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域中显示的图标。</span><span class="sxs-lookup"><span data-stu-id="0d69f-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="0d69f-105">通常情况下，应用程序，可以右键单击此图标以将命令发送到它表示应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d69f-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="0d69f-106">通过将相关联<xref:System.Windows.Forms.ContextMenu>组件<xref:System.Windows.Forms.NotifyIcon>组件时，可以将此功能添加到你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d69f-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d69f-107">如果您的应用程序，以将最小化在启动时显示的实例<xref:System.Windows.Forms.NotifyIcon>组件在任务栏中，设置主窗体的<xref:System.Windows.Forms.Form.WindowState%2A>属性<xref:System.Windows.Forms.FormWindowState.Minimized>并确保<xref:System.Windows.Forms.NotifyIcon>组件的<xref:System.Windows.Forms.NotifyIcon.Visible%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="0d69f-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="0d69f-108">要在设计时与 NotifyIcon 组件关联的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="0d69f-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1.  <span data-ttu-id="0d69f-109">添加<xref:System.Windows.Forms.NotifyIcon>组件到窗体中，和设置的重要属性，如<xref:System.Windows.Forms.NotifyIcon.Icon%2A>和<xref:System.Windows.Forms.NotifyIcon.Visible%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0d69f-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="0d69f-110">有关详细信息，请参阅[如何： 添加应用程序图标添加到使用 Windows 窗体 NotifyIcon 组件任务栏](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)。</span><span class="sxs-lookup"><span data-stu-id="0d69f-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2.  <span data-ttu-id="0d69f-111">添加<xref:System.Windows.Forms.ContextMenu>组件向 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="0d69f-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="0d69f-112">将菜单项添加到表示你想要在运行时提供的命令的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="0d69f-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="0d69f-113">这也是将菜单增强功能添加到这些菜单项，例如访问键的好时机。</span><span class="sxs-lookup"><span data-stu-id="0d69f-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3.  <span data-ttu-id="0d69f-114">设置<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>属性<xref:System.Windows.Forms.NotifyIcon>组件与你添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="0d69f-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="0d69f-115">此属性设置后，单击任务栏上的图标时，将显示的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="0d69f-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="0d69f-116">要以编程方式与 NotifyIcon 组件关联的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="0d69f-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1.  <span data-ttu-id="0d69f-117">创建的实例<xref:System.Windows.Forms.NotifyIcon>类和一个<xref:System.Windows.Forms.ContextMenu>类，与任何属性设置所需的应用程序 (<xref:System.Windows.Forms.NotifyIcon.Icon%2A>和<xref:System.Windows.Forms.NotifyIcon.Visible%2A>属性<xref:System.Windows.Forms.NotifyIcon>组件的菜单项<xref:System.Windows.Forms.ContextMenu>组件）。</span><span class="sxs-lookup"><span data-stu-id="0d69f-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2.  <span data-ttu-id="0d69f-118">设置<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>属性<xref:System.Windows.Forms.NotifyIcon>组件与你添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="0d69f-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="0d69f-119">此属性设置后，单击任务栏上的图标时，将显示的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="0d69f-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d69f-120">下面的代码示例创建一个基本的菜单结构。</span><span class="sxs-lookup"><span data-stu-id="0d69f-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="0d69f-121">你将需要自定义为适合你开发的应用程序的菜单选项。</span><span class="sxs-lookup"><span data-stu-id="0d69f-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="0d69f-122">此外，你将想要编写代码来处理<xref:System.Windows.Forms.MenuItem.Click>这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="0d69f-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _   
          (System.Environment.GetFolderPath _   
          (System.Environment.SpecialFolder.Personal)  _   
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
>  <span data-ttu-id="0d69f-123">必须初始化`notifyIcon1`和`contextMenu1,`你可以通过在你的窗体的构造函数中包括以下语句来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="0d69f-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="0d69f-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d69f-124">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="0d69f-125">如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标</span><span class="sxs-lookup"><span data-stu-id="0d69f-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/app-icons-to-the-taskbar-with-wf-notifyicon.md)  
 [<span data-ttu-id="0d69f-126">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="0d69f-126">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="0d69f-127">NotifyIcon 组件概述</span><span class="sxs-lookup"><span data-stu-id="0d69f-127">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
