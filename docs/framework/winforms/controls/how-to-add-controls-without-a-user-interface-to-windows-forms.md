---
title: 如何：向 Windows 窗体添加无用户界面的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 0a3e9ab5a048e085b192ffc0eb796caae1e58efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529457"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>如何：向 Windows 窗体添加无用户界面的控件
非可视控件 （或组件） 功能提供给你的应用程序。 不同于其他控件，组件不向用户提供的用户界面并因此不需要在 Windows 窗体设计器图面上显示。 后一个组件添加到窗体中，Windows 窗体设计器将在所有组件将都显示的窗体的底部显示可调整大小的任务栏。 控件现已添加到组件栏中后，你可选择的组件，设置其属性，就像任何其他控件在窗体上。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-add-a-component-to-a-windows-form"></a>若要将组件添加到 Windows 窗体  
  
1.  打开窗体。 有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。  
  
2.  在**工具箱**，单击某个组件，并将其拖到窗体。  
  
     此组件将出现在组件栏中。  
  
 而且，组件可以在运行时添加到窗体中。 这是常见的方案中，尤其是因为组件不具有 visual 表达式，不同于具有用户界面的控件。 在示例中，<xref:System.Windows.Forms.Timer>在运行时添加组件。 (请注意，Visual Studio 包含大量不同的计时器的; 在这种情况下，使用 Windows 窗体<xref:System.Windows.Forms.Timer>组件。 有关 Visual Studio 中不同的计时器的详细信息，请参阅[基于服务器的计时器简介](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。)  
  
> [!CAUTION]
>  组件通常具有必须为该组件可有效地工作设置的特定于控件的属性。 情况下<xref:System.Windows.Forms.Timer>下方的组件，你将设置`Interval`属性。 请确保，将组件添加到你的项目，你设置的属性需要该组件时。  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>若要以编程方式向 Windows 窗体添加一个组件  
  
1.  创建的实例<xref:System.Windows.Forms.Timer>在代码中的类。  
  
2.  设置`Interval`属性来确定的计时器刻度之间的时间。  
  
3.  配置任何其他必需的属性，为你的组件。  
  
     下面的代码演示如何创建<xref:System.Windows.Forms.Timer>与其`Interval`属性集。  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  通过引用恶意用户控件，则可能会公开您的本地计算机通过网络安全风险。 这仅会在恶意的用户创建破坏性的自定义控件，跟你错误地将其添加到你的项目的情况下是问题。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [如何：向 Windows 窗体添加 ActiveX 控件](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [如何：在 Windows 窗体之间复制控件](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [将控件置于 Windows 窗体上](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
