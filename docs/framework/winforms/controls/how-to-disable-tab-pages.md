---
title: "如何：禁用选项卡页"
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
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 20674a93459f42a793ddf5f7ee5dffb1fa122d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-disable-tab-pages"></a><span data-ttu-id="7c731-102">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="7c731-102">How to: Disable Tab Pages</span></span>
<span data-ttu-id="7c731-103">在某些情况下，你将想要限制对 Windows 窗体应用程序中可用的数据的访问。</span><span class="sxs-lookup"><span data-stu-id="7c731-103">On some occasions, you will want to restrict access to data that is available within your Windows Forms application.</span></span> <span data-ttu-id="7c731-104">这一个示例可能是当已在选项卡控件; 选项卡页中显示的数据管理员可以在你想要限制从来宾或较低级别的用户选项卡页的信息。</span><span class="sxs-lookup"><span data-stu-id="7c731-104">One example of this might be when you have data displayed in the tab pages of a tab control; administrators could have information on a tab page that you would want to restrict from guest or lower-level users.</span></span>  
  
### <a name="to-disable-tab-pages-programmatically"></a><span data-ttu-id="7c731-105">若要以编程方式禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="7c731-105">To disable tab pages programmatically</span></span>  
  
1.  <span data-ttu-id="7c731-106">编写代码来处理选项卡控件<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>事件。</span><span class="sxs-lookup"><span data-stu-id="7c731-106">Write code to handle the tab control's <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event.</span></span> <span data-ttu-id="7c731-107">这是当用户从一个选项卡切换到下一步时引发的事件。</span><span class="sxs-lookup"><span data-stu-id="7c731-107">This is the event that is raised when the user switches from one tab to the next.</span></span>  
  
2.  <span data-ttu-id="7c731-108">检查凭据。</span><span class="sxs-lookup"><span data-stu-id="7c731-108">Check credentials.</span></span> <span data-ttu-id="7c731-109">根据提供的信息，你可能想要检查用户已登录时使用的用户名称或某种其他形式的凭据，然后允许用户查看选项卡。</span><span class="sxs-lookup"><span data-stu-id="7c731-109">Depending upon the information presented, you may want to check the user name the user has logged in with or some other form of credentials before allowing the user to view the tab.</span></span>  
  
3.  <span data-ttu-id="7c731-110">如果用户有相应的凭据，显示被单击的选项卡。</span><span class="sxs-lookup"><span data-stu-id="7c731-110">If the user has appropriate credentials, display the tab that was clicked.</span></span> <span data-ttu-id="7c731-111">如果用户没有适当的凭据，显示一个消息框或某些其他用户界面以指示它们不具有访问权限，并返回到初始选项卡。</span><span class="sxs-lookup"><span data-stu-id="7c731-111">If the user does not have appropriate credentials, display a message box or some other user interface indicating that they do not have access, and return to the initial tab.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7c731-112">当你在生产应用程序中实现此功能时，你可以在窗体的过程中执行此凭据检查<xref:System.Windows.Forms.Form.Load>事件。</span><span class="sxs-lookup"><span data-stu-id="7c731-112">When you implement this functionality in your production applications, you can perform this credential check during the form's <xref:System.Windows.Forms.Form.Load> event.</span></span> <span data-ttu-id="7c731-113">这样，你可以在任何用户界面会显示，这是更简洁的编程方法前隐藏选项卡。</span><span class="sxs-lookup"><span data-stu-id="7c731-113">This will allow you to hide the tab before any user interface is shown, which is a much cleaner approach to programming.</span></span> <span data-ttu-id="7c731-114">使用下面的方法 (检查凭据并禁用期间选项卡<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>事件) 用于说明目的。</span><span class="sxs-lookup"><span data-stu-id="7c731-114">The methodology used below (checking credentials and disabling the tab during the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event) is for illustrative purposes.</span></span>  
  
4.  <span data-ttu-id="7c731-115">（可选） 如果你有两个以上的选项卡页，则显示原始版本不同的选项卡页。</span><span class="sxs-lookup"><span data-stu-id="7c731-115">Optionally, if you have more than two tab pages, display a tab page different from the original.</span></span>  
  
     <span data-ttu-id="7c731-116">在示例中，<xref:System.Windows.Forms.CheckBox>控件用于检查凭据，作为条件访问的选项卡将因应用程序的替代。</span><span class="sxs-lookup"><span data-stu-id="7c731-116">In the example below, a <xref:System.Windows.Forms.CheckBox> control is used in lieu of checking the credentials, as the criteria for access to the tab will vary by application.</span></span> <span data-ttu-id="7c731-117">当<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>引发事件时，如果凭据检查为 true （即，选中复选框） 和已选定选项卡是`TabPage2`（此示例中的机密信息的选项卡），然后`TabPage2`显示。</span><span class="sxs-lookup"><span data-stu-id="7c731-117">When the <xref:System.Windows.Forms.TabControl.SelectedIndexChanged> event is raised, if the credential check is true (that is, the check box is checked) and the selected tab is `TabPage2` (the tab with the confidential information, in this example), then `TabPage2` is displayed.</span></span> <span data-ttu-id="7c731-118">否则为`TabPage3`将显示一个消息框显示给用户，指出他们没有适当的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7c731-118">Otherwise, `TabPage3` is displayed and a message box is shown to the user, indicating they did not have appropriate access privileges.</span></span> <span data-ttu-id="7c731-119">下面的代码假定的窗体具有<xref:System.Windows.Forms.CheckBox>控件 (`CredentialCheck`) 和一个<xref:System.Windows.Forms.TabControl>带有三个选项卡页的控件。</span><span class="sxs-lookup"><span data-stu-id="7c731-119">The code below assumes a form with a <xref:System.Windows.Forms.CheckBox> control (`CredentialCheck`) and a <xref:System.Windows.Forms.TabControl> control with three tab pages.</span></span>  
  
    ```vb  
    Private Sub TabControl1_SelectedIndexChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles TabControl1.SelectedIndexChanged  
       ' Check Credentials Here  
  
       If CredentialCheck.Checked = True And _   
       TabControl1.SelectedTab Is TabPage2 Then  
          TabControl1.SelectedTab = TabPage2  
       ElseIf CredentialCheck.Checked = False _   
       And TabControl1.SelectedTab Is TabPage2 Then  
          MessageBox.Show _   
         ("Unable to load tab. You have insufficient access privileges.")  
          TabControl1.SelectedTab = TabPage3  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void tabControl1_SelectedIndexChanged(object sender, System.EventArgs e)  
    {  
        // Check Credentials Here  
  
        if ((CredentialCheck.Checked == true) && (tabControl1.SelectedTab == tabPage2))   
        {  
            tabControl1.SelectedTab = tabPage2;  
        }  
        else if ((CredentialCheck.Checked == false) && (tabControl1.SelectedTab == tabPage2))  
        {  
            MessageBox.Show("Unable to load tab. You have insufficient access privileges.");  
            tabControl1.SelectedTab = tabPage3;  
        }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void tabControl1_SelectedIndexChanged(  
          System::Object ^ sender,  
          System::EventArgs ^  e)  
       {  
          // Check Credentials Here  
          if ((CredentialCheck->Checked == true) &&  
              (tabControl1->SelectedTab == tabPage2))  
          {  
             tabControl1->SelectedTab = tabPage2;  
          }  
          else if ((CredentialCheck->Checked == false) &&  
                   (tabControl1->SelectedTab == tabPage2))  
          {  
             MessageBox::Show(String::Concat("Unable to load tab. ",  
                "You have insufficient access privileges."));  
             tabControl1->SelectedTab = tabPage3;  
          }  
       }  
    ```  
  
     <span data-ttu-id="7c731-120">（visual C#、 Visual c + +）将以下代码放在窗体的构造函数中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7c731-120">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7c731-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c731-121">See Also</span></span>  
 [<span data-ttu-id="7c731-122">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="7c731-122">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="7c731-123">如何：向选项卡页添加控件</span><span class="sxs-lookup"><span data-stu-id="7c731-123">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="7c731-124">如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡</span><span class="sxs-lookup"><span data-stu-id="7c731-124">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="7c731-125">如何：更改 Windows 窗体 TabControl 控件的外观</span><span class="sxs-lookup"><span data-stu-id="7c731-125">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
