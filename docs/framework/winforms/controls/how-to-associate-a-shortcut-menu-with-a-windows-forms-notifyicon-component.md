---
title: 将快捷菜单与 NotifyIcon 组件关联
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
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182253"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联
> [!NOTE]
> 以及<xref:System.Windows.Forms.MenuStrip>将<xref:System.Windows.Forms.ContextMenuStrip>功能替换和添加到早期版本的<xref:System.Windows.Forms.MainMenu><xref:System.Windows.Forms.ContextMenu>和 控件，<xref:System.Windows.Forms.MainMenu>并<xref:System.Windows.Forms.ContextMenu>保留用于向后兼容性和将来使用（如果选择）。  
  
 组件<xref:System.Windows.Forms.NotifyIcon>在任务栏的状态通知区域中显示一个图标。 通常，应用程序允许您右键单击此图标，将命令发送到它所代表的应用程序。 通过将<xref:System.Windows.Forms.ContextMenu>组件与<xref:System.Windows.Forms.NotifyIcon>组件关联，可以将此功能添加到应用程序中。  
  
> [!NOTE]
> 如果希望在启动时最小化应用程序，<xref:System.Windows.Forms.NotifyIcon>同时在任务栏中显示组件的实例，请将主窗体的属性<xref:System.Windows.Forms.Form.WindowState%2A>设置为<xref:System.Windows.Forms.FormWindowState.Minimized>，并确保<xref:System.Windows.Forms.NotifyIcon>组件的属性<xref:System.Windows.Forms.NotifyIcon.Visible%2A>设置为`true`。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>在设计时将快捷菜单与 NotifyIcon 组件关联  
  
1. 向窗体<xref:System.Windows.Forms.NotifyIcon>添加组件，并设置重要属性，如 和<xref:System.Windows.Forms.NotifyIcon.Icon%2A><xref:System.Windows.Forms.NotifyIcon.Visible%2A>属性。  
  
     有关详细信息，请参阅[：使用 Windows 窗体通知图标组件将应用程序图标添加到任务栏](app-icons-to-the-taskbar-with-wf-notifyicon.md)。  
  
2. 向<xref:System.Windows.Forms.ContextMenu>Windows 窗体添加组件。  
  
     将菜单项添加到表示要在运行时提供的命令的快捷菜单中。 这也是向这些菜单项（如访问键）添加菜单增强功能的好时机。  
  
3. 将<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A><xref:System.Windows.Forms.NotifyIcon>组件的属性设置为您添加的快捷菜单。  
  
     设置此属性后，单击任务栏上的图标时将显示快捷菜单。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>以编程方式将快捷菜单与 NotifyIcon 组件关联  
  
1. 创建<xref:System.Windows.Forms.NotifyIcon>类和<xref:System.Windows.Forms.ContextMenu>类的实例，包含应用程序所需的任何属性设置（<xref:System.Windows.Forms.NotifyIcon.Icon%2A>以及<xref:System.Windows.Forms.NotifyIcon.Visible%2A><xref:System.Windows.Forms.NotifyIcon>组件的属性、组件的<xref:System.Windows.Forms.ContextMenu>菜单项）。  
  
2. 将<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A><xref:System.Windows.Forms.NotifyIcon>组件的属性设置为您添加的快捷菜单。  
  
     设置此属性后，单击任务栏上的图标时将显示快捷菜单。  
  
    > [!NOTE]
    > 以下代码示例创建基本菜单结构。 您需要自定义菜单选项，以适应您正在开发的应用程序。 此外，您需要编写代码来处理这些菜单项<xref:System.Windows.Forms.MenuItem.Click>的事件。  
  
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
> 您必须初始化`notifyIcon1`，`contextMenu1,`并且可以通过在窗体的构造函数中包括以下语句来实现：  
  
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
