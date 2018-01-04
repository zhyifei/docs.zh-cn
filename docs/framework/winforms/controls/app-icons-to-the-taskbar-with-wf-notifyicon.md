---
title: "如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标"
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
f1_keywords: TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d795df8e8b514345632491fd6afdd618c2f18ec2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a>如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标
Windows 窗体<xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域中显示的一个图标。 若要在状态区域中显示多个图标，你必须有多个<xref:System.Windows.Forms.NotifyIcon>窗体上的组件。 若要设置控件显示的图标，使用<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。 也可以编写代码<xref:System.Windows.Forms.NotifyIcon.DoubleClick>事件处理程序，使该出现当用户双击的图标。 例如，你可以制作来配置由图标表示的后台进程的用户显示一个对话框。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.NotifyIcon>组件用于通知目的，警告用户操作或事件已发生或发生了某种类型的状态中的更改。 用于与应用程序的标准交互，应使用菜单、 工具栏和其他用户界面元素。  
  
### <a name="to-set-the-icon"></a>若要设置图标  
  
1.  将值赋给<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。 值必须为类型`System.Drawing.Icon`从.ico 文件进行加载。 在代码或通过单击省略号按钮，可以指定的图标文件 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.NotifyIcon.Icon%2A>中的属性**属性**窗口中，，然后选择中的文件**打开**出现对话框。  
  
2.  将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。  
  
3.  设置<xref:System.Windows.Forms.NotifyIcon.Text%2A>属性设置为相应的工具提示字符串。  
  
     在下面的代码示例中，路径为设置图标的位置为**我的文档**文件夹。 使用此位置是因为你可以采用大多数计算机运行 Windows 操作系统，将包含此文件夹。 选择此位置还允许具有最少的系统访问级别的用户安全地运行该应用程序。 下面的示例要求的窗体具有<xref:System.Windows.Forms.NotifyIcon>已添加的控件。 它还需要一个名为的图标文件`Icon.ico`。  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [如何：关联快捷菜单和 Windows 窗体 NotifyIcon 组件](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [NotifyIcon 组件](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [NotifyIcon 组件概述](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
