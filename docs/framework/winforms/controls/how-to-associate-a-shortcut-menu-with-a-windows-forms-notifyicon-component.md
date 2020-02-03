---
title: 关联快捷菜单与 NotifyIcon 组件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 392c04f73feaec201033ad76f9419a0e070bec70
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742044"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联
> [!NOTE]
> 尽管 <xref:System.Windows.Forms.MenuStrip> 和 <xref:System.Windows.Forms.ContextMenuStrip> 将功能替换并添加到以前版本的 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 控件中，但 <xref:System.Windows.Forms.MainMenu> 和 <xref:System.Windows.Forms.ContextMenu> 会保留，以实现向后兼容性和将来使用（如果你选择）。  
  
 <xref:System.Windows.Forms.NotifyIcon> 组件在任务栏的状态通知区域中显示一个图标。 通常情况下，应用程序允许您右键单击此图标，将命令发送到它代表的应用程序。 通过将 <xref:System.Windows.Forms.ContextMenu> 组件与 <xref:System.Windows.Forms.NotifyIcon> 组件相关联，你可以将此功能添加到应用程序。  
  
> [!NOTE]
> 如果希望在启动时最大程度地减少应用程序，同时在任务栏中显示 <xref:System.Windows.Forms.NotifyIcon> 组件的实例，请将主窗体的 <xref:System.Windows.Forms.Form.WindowState%2A> 属性设置为 <xref:System.Windows.Forms.FormWindowState.Minimized>，并确保 <xref:System.Windows.Forms.NotifyIcon> 组件的 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>在设计时将快捷菜单与 NotifyIcon 组件关联  
  
1. 将 <xref:System.Windows.Forms.NotifyIcon> 组件添加到窗体中，并设置重要属性，例如 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性。  
  
     有关详细信息，请参阅[如何：向任务栏添加应用程序图标以及 Windows 窗体 NotifyIcon 组件](app-icons-to-the-taskbar-with-wf-notifyicon.md)。  
  
2. 将 <xref:System.Windows.Forms.ContextMenu> 组件添加到 Windows 窗体。  
  
     将菜单项添加到快捷菜单，表示要在运行时使用的命令。 这也是向这些菜单项添加菜单增强功能（如访问密钥）的好时机。  
  
3. 将 <xref:System.Windows.Forms.NotifyIcon> 组件的 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 属性设置为添加的快捷菜单。  
  
     设置此属性后，单击任务栏上的图标时，将显示快捷菜单。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>以编程方式将快捷菜单与 NotifyIcon 组件相关联  
  
1. 创建 <xref:System.Windows.Forms.NotifyIcon> 类和 <xref:System.Windows.Forms.ContextMenu> 类的实例，其中包含应用程序所需的任何属性设置（<xref:System.Windows.Forms.NotifyIcon.Icon%2A> 和 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性（<xref:System.Windows.Forms.NotifyIcon> 组件的菜单项）。<xref:System.Windows.Forms.ContextMenu>  
  
2. 将 <xref:System.Windows.Forms.NotifyIcon> 组件的 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 属性设置为添加的快捷菜单。  
  
     设置此属性后，单击任务栏上的图标时，将显示快捷菜单。  
  
    > [!NOTE]
    > 下面的代码示例创建一个基本菜单结构。 您将需要自定义菜单选项，使其适合您正在开发的应用程序。 此外，您还需要编写代码来处理这些菜单项的 <xref:System.Windows.Forms.MenuItem.Click> 事件。  
  
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
> 必须通过在窗体的构造函数中包含以下语句来初始化 `notifyIcon1` 和 `contextMenu1,`：  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon 组件](notifyicon-component-windows-forms.md)
- [NotifyIcon 组件概述](notifyicon-component-overview-windows-forms.md)
