---
title: 如何：将应用程序图标添加到使用 Windows 窗体 NotifyIcon 组件任务栏
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
ms.openlocfilehash: 925134e4a0317322d7a4f4cfdc9ac8e3780cf9e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54650676"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="95c9d-102">如何：将应用程序图标添加到使用 Windows 窗体 NotifyIcon 组件任务栏</span><span class="sxs-lookup"><span data-stu-id="95c9d-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="95c9d-103">Windows 窗体<xref:System.Windows.Forms.NotifyIcon>组件在任务栏的状态通知区域显示一个图标。</span><span class="sxs-lookup"><span data-stu-id="95c9d-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="95c9d-104">若要在状态区域中显示多个图标，必须有多个<xref:System.Windows.Forms.NotifyIcon>窗体上的组件。</span><span class="sxs-lookup"><span data-stu-id="95c9d-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="95c9d-105">若要设置控件显示的图标，使用<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="95c9d-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="95c9d-106">此外可以编写代码<xref:System.Windows.Forms.NotifyIcon.DoubleClick>事件处理程序，以便当用户双击该图标出现该问题。</span><span class="sxs-lookup"><span data-stu-id="95c9d-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="95c9d-107">例如，您能够为用户配置后台进程的图标表示显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="95c9d-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95c9d-108"><xref:System.Windows.Forms.NotifyIcon>组件用于通知目的，警告用户操作或事件已发生或已在某种类型的状态更改。</span><span class="sxs-lookup"><span data-stu-id="95c9d-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="95c9d-109">应与应用程序的标准交互使用菜单、 工具栏和其他用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="95c9d-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="95c9d-110">若要设置图标</span><span class="sxs-lookup"><span data-stu-id="95c9d-110">To set the icon</span></span>  
  
1.  <span data-ttu-id="95c9d-111">将一个值赋给<xref:System.Windows.Forms.NotifyIcon.Icon%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="95c9d-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="95c9d-112">值必须属于类型`System.Drawing.Icon`和可以从.ico 文件加载。</span><span class="sxs-lookup"><span data-stu-id="95c9d-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="95c9d-113">在代码中，或单击省略号按钮，可以指定图标文件 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.NotifyIcon.Icon%2A>中的属性**属性**窗口中，，然后选择中的文件**打开**出现的对话框。</span><span class="sxs-lookup"><span data-stu-id="95c9d-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2.  <span data-ttu-id="95c9d-114">将 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="95c9d-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3.  <span data-ttu-id="95c9d-115">设置<xref:System.Windows.Forms.NotifyIcon.Text%2A>属性设置为一个合适的工具提示字符串。</span><span class="sxs-lookup"><span data-stu-id="95c9d-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="95c9d-116">在下面的代码示例中，将路径设置图标的位置是**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="95c9d-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="95c9d-117">使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机将包含该文件夹。</span><span class="sxs-lookup"><span data-stu-id="95c9d-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="95c9d-118">选择此位置，用户还可以具有最少的系统访问级别来安全地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="95c9d-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="95c9d-119">下面的示例要求具有的窗体<xref:System.Windows.Forms.NotifyIcon>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="95c9d-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="95c9d-120">它还需要一个名为的图标文件`Icon.ico`。</span><span class="sxs-lookup"><span data-stu-id="95c9d-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95c9d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="95c9d-121">See also</span></span>
- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="95c9d-122">如何：使用 Windows 窗体 NotifyIcon 组件关联快捷菜单</span><span class="sxs-lookup"><span data-stu-id="95c9d-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="95c9d-123">NotifyIcon 组件</span><span class="sxs-lookup"><span data-stu-id="95c9d-123">NotifyIcon Component</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)
- [<span data-ttu-id="95c9d-124">NotifyIcon 组件概述</span><span class="sxs-lookup"><span data-stu-id="95c9d-124">NotifyIcon Component Overview</span></span>](../../../../docs/framework/winforms/controls/notifyicon-component-overview-windows-forms.md)
