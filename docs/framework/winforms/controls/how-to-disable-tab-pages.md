---
title: 如何：禁用选项卡页
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tab pages [Windows Forms], hiding in forms
- TabControl control [Windows Forms], disabling pages
ms.assetid: adcc6618-8a34-4ee1-bbe3-47e732de6a59
ms.openlocfilehash: 94d8522a71fcd565ae8f994d73ffe4c46fcf7ce3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534262"
---
# <a name="how-to-disable-tab-pages"></a>如何：禁用选项卡页
在某些情况下，你将想要限制对 Windows 窗体应用程序中可用的数据的访问。 这一个示例可能是当已在选项卡控件; 选项卡页中显示的数据管理员可以在你想要限制从来宾或较低级别的用户选项卡页的信息。  
  
### <a name="to-disable-tab-pages-programmatically"></a>若要以编程方式禁用选项卡页  
  
1.  编写代码来处理选项卡控件<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>事件。 这是当用户从一个选项卡切换到下一步时引发的事件。  
  
2.  检查凭据。 根据提供的信息，你可能想要检查用户已登录时使用的用户名称或某种其他形式的凭据，然后允许用户查看选项卡。  
  
3.  如果用户有相应的凭据，显示被单击的选项卡。 如果用户没有适当的凭据，显示一个消息框或某些其他用户界面以指示它们不具有访问权限，并返回到初始选项卡。  
  
    > [!NOTE]
    >  当你在生产应用程序中实现此功能时，你可以在窗体的过程中执行此凭据检查<xref:System.Windows.Forms.Form.Load>事件。 这样，你可以在任何用户界面会显示，这是更简洁的编程方法前隐藏选项卡。 使用下面的方法 (检查凭据并禁用期间选项卡<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>事件) 用于说明目的。  
  
4.  （可选） 如果你有两个以上的选项卡页，则显示原始版本不同的选项卡页。  
  
     在示例中，<xref:System.Windows.Forms.CheckBox>控件用于检查凭据，作为条件访问的选项卡将因应用程序的替代。 当<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>引发事件时，如果凭据检查为 true （即，选中复选框） 和已选定选项卡是`TabPage2`（此示例中的机密信息的选项卡），然后`TabPage2`显示。 否则为`TabPage3`将显示一个消息框显示给用户，指出他们没有适当的访问权限。 下面的代码假定的窗体具有<xref:System.Windows.Forms.CheckBox>控件 (`CredentialCheck`) 和一个<xref:System.Windows.Forms.TabControl>带有三个选项卡页的控件。  
  
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
  
     （visual C#、 Visual c + +）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=   
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>请参阅  
 [TabControl 控件概述](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [如何：向选项卡页添加控件](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)  
 [如何：更改 Windows 窗体 TabControl 控件的外观](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
