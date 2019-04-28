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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802578"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="1cd91-102">如何：显示 Windows 窗体的对话框</span><span class="sxs-lookup"><span data-stu-id="1cd91-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="1cd91-103">在应用程序中显示的任何其他形式的相同方式显示一个对话框。</span><span class="sxs-lookup"><span data-stu-id="1cd91-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="1cd91-104">启动窗体应用程序运行时，会自动加载。</span><span class="sxs-lookup"><span data-stu-id="1cd91-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="1cd91-105">若要使第二个窗体或应用程序中出现的对话框中，编写代码以加载并显示它。</span><span class="sxs-lookup"><span data-stu-id="1cd91-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="1cd91-106">同样，若要使窗体或对话框消失，可编写代码以卸载或将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="1cd91-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="1cd91-107">若要显示的对话框</span><span class="sxs-lookup"><span data-stu-id="1cd91-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="1cd91-108">导航到想要打开对话框的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1cd91-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="1cd91-109">这可以选择菜单命令时，单击一个按钮时，或者任何其他事件发生时。</span><span class="sxs-lookup"><span data-stu-id="1cd91-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="1cd91-110">在事件处理程序添加代码以打开对话框。</span><span class="sxs-lookup"><span data-stu-id="1cd91-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="1cd91-111">在此示例中，按钮单击事件用于显示对话框中：</span><span class="sxs-lookup"><span data-stu-id="1cd91-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
