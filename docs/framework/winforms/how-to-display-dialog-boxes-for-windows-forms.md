---
title: 如何：显示 Windows 窗体的对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311079"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a>如何：显示 Windows 窗体的对话框
在应用程序中显示的任何其他形式的相同方式显示一个对话框。 启动窗体应用程序运行时，会自动加载。 若要使第二个窗体或应用程序中出现的对话框中，编写代码以加载并显示它。 同样，若要使窗体或对话框消失，可编写代码以卸载或将其隐藏。  
  
### <a name="to-display-a-dialog-box"></a>若要显示的对话框  
  
1. 导航到想要打开对话框的事件处理程序。 这可以选择菜单命令时，单击一个按钮时，或者任何其他事件发生时。  
  
2. 在事件处理程序添加代码以打开对话框。 在此示例中，按钮单击事件用于显示对话框中：  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:   
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
