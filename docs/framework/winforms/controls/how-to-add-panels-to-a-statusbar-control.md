---
title: 如何：向 StatusBar 控件添加面板
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- panels [Windows Forms], status bars
- status bars [Windows Forms], adding panels
- StatusBar control [Windows Forms], adding panels
ms.assetid: 835e3902-288c-4c38-9d69-0696d8695009
ms.openlocfilehash: 386c8cae425c458ddf4c446a454ae4213761e651
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142194"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="a9a89-102">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="a9a89-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a9a89-103"><xref:System.Windows.Forms.StatusStrip>和<xref:System.Windows.Forms.ToolStripStatusLabel>控件将 功能替换并添加到<xref:System.Windows.Forms.StatusBar><xref:System.Windows.Forms.StatusBarPanel>和 控件;但是，如果<xref:System.Windows.Forms.StatusBar>愿意<xref:System.Windows.Forms.StatusBarPanel>，将保留 和 控件以进行向后兼容性和未来使用。</span><span class="sxs-lookup"><span data-stu-id="a9a89-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="a9a89-104">[StatusBar 控件](statusbar-control-windows-forms.md)中的可编程区域由<xref:System.Windows.Forms.StatusBarPanel>类的实例组成。</span><span class="sxs-lookup"><span data-stu-id="a9a89-104">The programmable area within a [StatusBar Control](statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="a9a89-105">这些通过添加到类添加<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>。</span><span class="sxs-lookup"><span data-stu-id="a9a89-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="a9a89-106">将面板添加到状态栏</span><span class="sxs-lookup"><span data-stu-id="a9a89-106">To add panels to a status bar</span></span>  
  
1. <span data-ttu-id="a9a89-107">在此过程中，通过将状态栏面板添加到 中<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>，创建状态栏面板。</span><span class="sxs-lookup"><span data-stu-id="a9a89-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="a9a89-108">使用通过<xref:System.Windows.Forms.StatusBar.Panels%2A>属性传递的索引为各个面板指定属性设置。</span><span class="sxs-lookup"><span data-stu-id="a9a89-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="a9a89-109">在下面的代码示例中，为图标的位置设置的路径是 **"我的文档"** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a9a89-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="a9a89-110">使用此位置是因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此文件夹。</span><span class="sxs-lookup"><span data-stu-id="a9a89-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="a9a89-111">选择此位置还允许系统访问级别最低的用户安全地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a9a89-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a9a89-112">下面的示例需要已添加控件的<xref:System.Windows.Forms.StatusBar>窗体。</span><span class="sxs-lookup"><span data-stu-id="a9a89-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a9a89-113"><xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>是一个基于零的集合，因此代码应相应地继续。</span><span class="sxs-lookup"><span data-stu-id="a9a89-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
    ```vb  
    Public Sub CreateStatusBarPanels()  
    ' Create panels and set text property.  
       StatusBar1.Panels.Add("One")  
       StatusBar1.Panels.Add("Two")  
       StatusBar1.Panels.Add("Three")  
    ' Set properties of StatusBar panels.  
    ' Set AutoSize property of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(1).AutoSize = StatusBarPanelAutoSize.Contents  
       StatusBar1.Panels(2).AutoSize = StatusBarPanelAutoSize.Contents  
    ' Set BorderStyle property of panels.  
       StatusBar1.Panels(0).BorderStyle = StatusBarPanelBorderStyle.Raised  
       StatusBar1.Panels(1).BorderStyle = StatusBarPanelBorderStyle.Sunken  
       StatusBar1.Panels(2).BorderStyle = StatusBarPanelBorderStyle.Raised  
    ' Set Icon property of third panel. You should replace the bolded  
    ' icon in the sample below with an icon of your own choosing.  
       StatusBar1.Panels(2).Icon = New _
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
       StatusBar1.ShowPanels = True  
    End Sub  
    ```  
  
    ```csharp  
    public void CreateStatusBarPanels()  
    {  
       // Create panels and set text property.  
       statusBar1.Panels.Add("One");  
       statusBar1.Panels.Add("Two");  
       statusBar1.Panels.Add("Three");  
       // Set properties of StatusBar panels.  
       // Set AutoSize property of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[1].AutoSize = StatusBarPanelAutoSize.Contents;  
       statusBar1.Panels[2].AutoSize = StatusBarPanelAutoSize.Contents;  
       // Set BorderStyle property of panels.  
       statusBar1.Panels[0].BorderStyle =  
          StatusBarPanelBorderStyle.Raised;  
       statusBar1.Panels[1].BorderStyle = StatusBarPanelBorderStyle.Sunken;  
       statusBar1.Panels[2].BorderStyle = StatusBarPanelBorderStyle.Raised;  
       // Set Icon property of third panel. You should replace the bolded  
       // icon in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       statusBar1.Panels[2].Icon =
          new System.Drawing.Icon (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Icon.ico");  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void CreateStatusBarPanels()  
       {  
          // Create panels and set text property.  
          statusBar1->Panels->Add("One");  
          statusBar1->Panels->Add("Two");  
          statusBar1->Panels->Add("Three");  
          // Set properties of StatusBar panels.  
          // Set AutoSize property of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[1]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          statusBar1->Panels[2]->AutoSize =  
             StatusBarPanelAutoSize::Contents;  
          // Set BorderStyle property of panels.  
          statusBar1->Panels[0]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          statusBar1->Panels[1]->BorderStyle =  
             StatusBarPanelBorderStyle::Sunken;  
          statusBar1->Panels[2]->BorderStyle =  
             StatusBarPanelBorderStyle::Raised;  
          // Set Icon property of third panel.  
          // You should replace the bolded image
          // in the sample below with an icon of your own choosing.  
          statusBar1->Panels[2]->Icon =  
             gcnew System::Drawing::Icon(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Icon.ico"));  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a9a89-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9a89-114">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <span data-ttu-id="a9a89-115">[“集合编辑器”对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a9a89-115">[Collection Editor Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span></span>
- [<span data-ttu-id="a9a89-116">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="a9a89-116">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="a9a89-117">演练：在运行时更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="a9a89-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="a9a89-118">如何：确定 Windows 窗体 StatusBar 控件中被单击的面板</span><span class="sxs-lookup"><span data-stu-id="a9a89-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="a9a89-119">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="a9a89-119">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
