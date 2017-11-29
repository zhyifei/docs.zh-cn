---
title: "如何：在 Windows 窗体 RichTextBox 控件中保存文件"
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
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d28aeaefca6f8aa13607f1c1e6f72557ef536754
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>如何：在 Windows 窗体 RichTextBox 控件中保存文件
Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件可以编写它在几种格式之一显示的信息：  
  
-   纯文本  
  
-   Unicode 纯文本  
  
-   丰富文本格式 (RTF)  
  
-   RTF 空格代替 OLE 对象  
  
-   使用的 OLE 对象文本表示形式的纯文本  
  
 若要保存文件时，调用<xref:System.Windows.Forms.RichTextBox.SaveFile%2A>方法。 你还可以使用**SaveFile**方法以将数据保存到流。 有关更多信息，请参见<xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>。  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a>将控件的内容保存到文件  
  
1.  确定要保存的文件的路径。  
  
     若要在实际应用程序中执行此操作，通常可以使用<xref:System.Windows.Forms.SaveFileDialog>组件。 有关概述，请参阅[SaveFileDialog 组件概述](../../../../docs/framework/winforms/controls/savefiledialog-component-overview-windows-forms.md)。  
  
2.  调用<xref:System.Windows.Forms.RichTextBox.SaveFile%2A>方法<xref:System.Windows.Forms.RichTextBox>控件中，指定要保存的文件和 （可选） 的文件类型。 如果调用具有一个文件名称作为其唯一的自变量的方法，则将为 rtf 格式保存该文件。 若要指定其他文件类型，请使用 <xref:System.Windows.Forms.RichTextBoxStreamType> 枚举的值作为其第二个参数来调用该方法。  
  
     在下面的示例中，路径为设置多格式文本文件的位置为**我的文档**文件夹。 使用此位置是因为你可以采用大多数计算机运行 Windows 操作系统，将包含此文件夹。 选择此位置还允许具有最少的系统访问级别的用户安全地运行该应用程序。 下面的示例假定的窗体具有<xref:System.Windows.Forms.RichTextBox>已添加的控件。  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  此示例在文件尚未存在时创建新文件。 如果应用程序需要创建一个文件，该应用程序将需要的文件夹的创建访问权限。 可使用访问控制列表设置权限。 如果该文件已存在，应用程序需要只写访问权限，较弱的特权。 如果可能，它会在部署期间，创建文件和仅授予读取访问权限单个文件，而不是创建一个文件夹的访问更安全。 此外，较安全的做法是将数据写入用户文件夹，而不是根文件夹或“Program Files”文件夹。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 控件](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
