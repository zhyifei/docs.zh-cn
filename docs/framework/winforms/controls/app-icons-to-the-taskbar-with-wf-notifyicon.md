---
title: 如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: c7658a3a1c72c3fed4033e644d0dd776b06ee1a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="28514-102">如何：使用 Windows 窗体 NotifyIcon 组件向任务栏添加应用程序图标</span><span class="sxs-lookup"><span data-stu-id="28514-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="28514-103">Windows 窗体<xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域中显示的一个图标。</span><span class="sxs-lookup"><span data-stu-id="28514-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="28514-104">若要在状态区域中显示多个图标，你必须有多个<xref:System.Windows.Forms.NotifyIcon>窗体上的组件。</span><span class="sxs-lookup"><span data-stu-id="28514-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="28514-105">若要设置控件显示的图标，使用<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="28514-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="28514-106">也可以编写代码<xref:System.Windows.Forms.NotifyIcon.DoubleClick>事件处理程序，使该出现当用户双击的图标。</span><span class="sxs-lookup"><span data-stu-id="28514-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="28514-107">例如，你可以制作来配置由图标表示的后台进程的用户显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="28514-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28514-108"><xref:System.Windows.Forms.NotifyIcon>组件用于通知目的，警告用户操作或事件已发生或发生了某种类型的状态中的更改。</span><span class="sxs-lookup"><span data-stu-id="28514-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="28514-109">用于与应用程序的标准交互，应使用菜单、 工具栏和其他用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="28514-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="28514-110">若要设置图标</span><span class="sxs-lookup"><span data-stu-id="28514-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="28514-111">将值赋给<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="28514-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="28514-112">值必须为类型`System.Drawing.Icon`从.ico 文件进行加载。</span><span class="sxs-lookup"><span data-stu-id="28514-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="28514-113">在代码或通过单击省略号按钮，可以指定的图标文件 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.NotifyIcon.Icon%2A>中的属性**属性**窗口中，，然后选择中的文件**打开**出现对话框。</span><span class="sxs-lookup"><span data-stu-id="28514-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="28514-114">将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="28514-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="28514-115">设置<xref:System.Windows.Forms.NotifyIcon.Text%2A>属性设置为相应的工具提示字符串。</span><span class="sxs-lookup"><span data-stu-id="28514-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="28514-116">在下面的代码示例中，路径为设置图标的位置为**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="28514-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="28514-117">使用此位置是因为你可以采用大多数计算机运行 Windows 操作系统，将包含此文件夹。</span><span class="sxs-lookup"><span data-stu-id="28514-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="28514-118">选择此位置还允许具有最少的系统访问级别的用户安全地运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="28514-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="28514-119">下面的示例要求的窗体具有<xref:System.Windows.Forms.NotifyIcon>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="28514-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="28514-120">它还需要一个名为的图标文件`Icon.ico`。</span><span class="sxs-lookup"><span data-stu-id="28514-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="28514-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="28514-121">See Also</span></span>  
 <xref:System.Windows.Forms.NotifyIcon>  
 <xref:System.Windows.Forms.NotifyIcon.Icon%2A>  
 [<span data-ttu-id="28514-122">如何：关联快捷菜单和 Windows 窗体 NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="28514-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)  
 [<span data-ttu-id="28514-123">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="28514-123">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)  
 [<span data-ttu-id="28514-124">NotifyIcon 组件概述</span><span class="sxs-lookup"><span data-stu-id="28514-124">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
