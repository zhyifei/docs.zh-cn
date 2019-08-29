---
title: 如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联
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
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922765"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>如何：将快捷菜单与 Windows 窗体 NotifyIcon 组件关联
> [!NOTE]
> 尽管<xref:System.Windows.Forms.MenuStrip>和<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu>将功能替换为以前版本的和控件, 并将其保留以实现后向兼容性和将来使用 (如果你选择)。 <xref:System.Windows.Forms.ContextMenuStrip>  
  
 <xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域中显示一个图标。 通常情况下, 应用程序允许您右键单击此图标, 将命令发送到它代表的应用程序。 通过将<xref:System.Windows.Forms.ContextMenu>组件<xref:System.Windows.Forms.NotifyIcon>与组件关联, 你可以将此功能添加到应用程序。  
  
> [!NOTE]
> 如果希望在启动时最大程度地减少应用程序, 同时在任务栏<xref:System.Windows.Forms.NotifyIcon>中显示组件的实例, 请将主窗<xref:System.Windows.Forms.Form.WindowState%2A>体的<xref:System.Windows.Forms.FormWindowState.Minimized>属性设置<xref:System.Windows.Forms.NotifyIcon>为, 并确保<xref:System.Windows.Forms.NotifyIcon.Visible%2A>组件的属性设置为`true`。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>在设计时将快捷菜单与 NotifyIcon 组件关联  
  
1. 将组件添加到窗体, 并设置重要属性, 如<xref:System.Windows.Forms.NotifyIcon.Icon%2A>和<xref:System.Windows.Forms.NotifyIcon.Visible%2A>属性。 <xref:System.Windows.Forms.NotifyIcon>  
  
     有关详细信息，请参阅[如何：向任务栏添加应用程序图标, 其中包含 Windows 窗体 NotifyIcon](app-icons-to-the-taskbar-with-wf-notifyicon.md)组件。  
  
2. <xref:System.Windows.Forms.ContextMenu>将组件添加到 Windows 窗体。  
  
     将菜单项添加到快捷菜单, 表示要在运行时使用的命令。 这也是向这些菜单项添加菜单增强功能 (如访问密钥) 的好时机。  
  
3. 将<xref:System.Windows.Forms.NotifyIcon>组件<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>的属性设置为添加的快捷菜单。  
  
     设置此属性后, 单击任务栏上的图标时, 将显示快捷菜单。  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>以编程方式将快捷菜单与 NotifyIcon 组件相关联  
  
1. <xref:System.Windows.Forms.NotifyIcon>创建类<xref:System.Windows.Forms.NotifyIcon.Visible%2A> <xref:System.Windows.Forms.NotifyIcon.Icon%2A> <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.NotifyIcon>和类的实例, 其中包含应用程序所需的任何属性设置 (组件的属性、组件的菜单项) <xref:System.Windows.Forms.ContextMenu>组件)。  
  
2. 将<xref:System.Windows.Forms.NotifyIcon>组件<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>的属性设置为添加的快捷菜单。  
  
     设置此属性后, 单击任务栏上的图标时, 将显示快捷菜单。  
  
    > [!NOTE]
    > 下面的代码示例创建一个基本菜单结构。 您将需要自定义菜单选项, 使其适合您正在开发的应用程序。 此外, 您还需要编写代码来处理这些菜单<xref:System.Windows.Forms.MenuItem.Click>项的事件。  
  
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
> 您必须通过`notifyIcon1`在`contextMenu1,`您的窗体的构造函数中包含以下语句来初始化和可执行的操作:  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [如何：向任务栏添加应用程序图标, 其中包含 Windows 窗体 NotifyIcon 组件](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon 组件](notifyicon-component-windows-forms.md)
- [NotifyIcon 组件概述](notifyicon-component-overview-windows-forms.md)
