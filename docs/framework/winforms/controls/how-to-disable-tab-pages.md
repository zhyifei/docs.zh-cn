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
ms.openlocfilehash: 9074aedb81a485267dc4faff92e0fe8d0d3b467f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182162"
---
# <a name="how-to-disable-tab-pages"></a>如何：禁用选项卡页
在某些情况下，您需要限制对 Windows 窗体应用程序中可用的数据的访问。 其中一个示例可能是，当您在选项卡控件的选项卡页中显示数据时;例如，在选项卡控件的选项卡页中显示数据时，可能会显示此情况。管理员可以在选项卡页上包含您希望从来宾或较低级别用户限制的信息。  
  
### <a name="to-disable-tab-pages-programmatically"></a>以编程方式禁用选项卡页  
  
1. 编写代码来处理选项卡控件的事件<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>。 这是当用户从一个选项卡切换到下一个选项卡时引发的事件。  
  
2. 检查凭据。 根据提供的信息，您可能需要在允许用户查看选项卡之前检查用户已登录的用户名或其他形式的凭据。  
  
3. 如果用户具有适当的凭据，请显示单击的选项卡。 如果用户没有适当的凭据，则显示消息框或其他一些用户界面，指示他们没有访问权限，然后返回到初始选项卡。  
  
    > [!NOTE]
    > 在生产应用程序中实现此功能时，可以在窗体<xref:System.Windows.Forms.Form.Load>的事件期间执行此凭据检查。 这将允许您在显示任何用户界面之前隐藏选项卡，这是一种更简洁的编程方法。 下面使用的方法（在<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>活动期间检查凭据并禁用选项卡）用于说明目的。  
  
4. 或者，如果您有两个以上的选项卡页，则显示与原始页面不同的选项卡页。  
  
     在下面的示例中，使用<xref:System.Windows.Forms.CheckBox>控件来代替检查凭据，因为访问选项卡的条件因应用程序而异。 引发<xref:System.Windows.Forms.TabControl.SelectedIndexChanged>事件时，如果凭据检查为 true（即选中复选框），并且所选选项卡为`TabPage2`（在此示例中显示带有机密信息的选项卡），则`TabPage2`显示。 否则，`TabPage3`将显示消息框，并显示一个消息框，指示用户没有适当的访问权限。 下面的代码假定一个包含控件<xref:System.Windows.Forms.CheckBox>（`CredentialCheck`） 的<xref:System.Windows.Forms.TabControl>窗体和具有三个选项卡页的控件。  
  
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
  
     （视觉 C#，视觉C++）将以下代码放在窗体的构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.tabControl1.SelectedIndexChanged +=
       new System.EventHandler(this.tabControl1_SelectedIndexChanged);  
    ```  
  
    ```cpp  
    this->tabControl1->SelectedIndexChanged +=  
       gcnew System::EventHandler(this, &Form1::tabControl1_SelectedIndexChanged);  
    ```  
  
## <a name="see-also"></a>另请参阅

- [TabControl 控件概述](tabcontrol-control-overview-windows-forms.md)
- [如何：将控件添加到选项卡页](how-to-add-a-control-to-a-tab-page.md)
- [如何：使用 Windows 窗体 TabControl 添加和移除选项卡](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
- [如何：更改 Windows 窗体 TabControl 的外观](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
