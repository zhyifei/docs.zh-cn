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
ms.openlocfilehash: 0c7c843fd3b837cb221e055bd96f735fb5e9c4ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713276"
---
# <a name="how-to-add-panels-to-a-statusbar-control"></a><span data-ttu-id="9b849-102">如何：向 StatusBar 控件添加面板</span><span class="sxs-lookup"><span data-stu-id="9b849-102">How to: Add Panels to a StatusBar Control</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="9b849-103"><xref:System.Windows.Forms.StatusStrip>并<xref:System.Windows.Forms.ToolStripStatusLabel>控件替换，并将功能添加到<xref:System.Windows.Forms.StatusBar>并<xref:System.Windows.Forms.StatusBarPanel>控制; 但是，<xref:System.Windows.Forms.StatusBar>和<xref:System.Windows.Forms.StatusBarPanel>控件将保留用于向后兼容性并供将来使用，如果你选择。</span><span class="sxs-lookup"><span data-stu-id="9b849-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="9b849-104">中的可编程区域[StatusBar 控件](statusbar-control-windows-forms.md)控件由实例构成<xref:System.Windows.Forms.StatusBarPanel>类。</span><span class="sxs-lookup"><span data-stu-id="9b849-104">The programmable area within a [StatusBar Control](statusbar-control-windows-forms.md) control consists of instances of the <xref:System.Windows.Forms.StatusBarPanel> class.</span></span> <span data-ttu-id="9b849-105">通过添加到添加这些<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>类。</span><span class="sxs-lookup"><span data-stu-id="9b849-105">These are added through additions to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> class.</span></span>  
  
### <a name="to-add-panels-to-a-status-bar"></a><span data-ttu-id="9b849-106">若要添加到状态栏面板</span><span class="sxs-lookup"><span data-stu-id="9b849-106">To add panels to a status bar</span></span>  
  
1.  <span data-ttu-id="9b849-107">在过程中，通过将它们添加到创建状态栏面板<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>。</span><span class="sxs-lookup"><span data-stu-id="9b849-107">In a procedure, create status-bar panels by adding them to the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span> <span data-ttu-id="9b849-108">指定属性设置为通过其索引的各个面板传递<xref:System.Windows.Forms.StatusBar.Panels%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9b849-108">Specify property settings for individual panels by using its index passed through the <xref:System.Windows.Forms.StatusBar.Panels%2A> property.</span></span>  
  
     <span data-ttu-id="9b849-109">在下面的代码示例中，将路径设置图标的位置是**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9b849-109">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="9b849-110">使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机将包含该文件夹。</span><span class="sxs-lookup"><span data-stu-id="9b849-110">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="9b849-111">选择此位置还允许具有最少的系统访问级别的用户安全地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9b849-111">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="9b849-112">下面的示例要求具有的窗体<xref:System.Windows.Forms.StatusBar>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="9b849-112">The following example requires a form with a <xref:System.Windows.Forms.StatusBar> control already added.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b849-113"><xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>是从零开始的集合，因此代码应进行相应处理。</span><span class="sxs-lookup"><span data-stu-id="9b849-113">The <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection> is a zero-based collection, so code should proceed accordingly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b849-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b849-114">See also</span></span>
- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- <span data-ttu-id="9b849-115">[集合编辑器对话框](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9b849-115">[Collection Editor Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/xc4yyekt(v=vs.100))</span></span>
- [<span data-ttu-id="9b849-116">如何：设置状态栏面板的大小</span><span class="sxs-lookup"><span data-stu-id="9b849-116">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)
- [<span data-ttu-id="9b849-117">演练：在运行时的更新状态栏信息</span><span class="sxs-lookup"><span data-stu-id="9b849-117">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)
- [<span data-ttu-id="9b849-118">如何：确定已单击 Windows 窗体 StatusBar 控件中的面板</span><span class="sxs-lookup"><span data-stu-id="9b849-118">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [<span data-ttu-id="9b849-119">StatusBar 控件概述</span><span class="sxs-lookup"><span data-stu-id="9b849-119">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)
