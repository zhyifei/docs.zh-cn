---
title: 通过 RichTextBox 控件保存文件
ms.date: 03/30/2017
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
ms.openlocfilehash: a87b93a53347aeba54f944b0f4c455aa272ea243
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744817"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤을 사용하여 파일 저장

Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件可以编写它所显示的信息，其中一种格式如下：

- 일반 텍스트

- Unicode 纯文本

- Rtf 格式（RTF）

- 用空格代替 OLE 对象的 RTF

- 带有 OLE 对象的文本化表示形式的纯文本

若要保存文件，请调用 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 方法。 还可以使用**SaveFile**方法将数据保存到流中。 자세한 내용은 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>를 참조하세요.

### <a name="to-save-the-contents-of-the-control-to-a-file"></a>将控件的内容保存到文件中

1. 确定要保存的文件的路径。

    若要在实际应用程序中执行此操作，通常要使用 <xref:System.Windows.Forms.SaveFileDialog> 组件。 有关概述，请参阅[SaveFileDialog 组件概述](savefiledialog-component-overview-windows-forms.md)。

2. 调用 <xref:System.Windows.Forms.RichTextBox> 控件的 <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> 方法，并指定要保存的文件，还可以指定一个文件类型。 如果调用方法时将文件名作为其唯一参数，则该文件将保存为 RTF 格式。 다른 파일 형식을 지정하려면 <xref:System.Windows.Forms.RichTextBoxStreamType> 열거형의 값을 두 번째 인수로 사용하여 메서드를 호출합니다.

    在下面的示例中，为 rtf 文件的位置设置的路径是 "**我的文档**" 文件夹。 使用此位置的原因是，你可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。 选择此位置还允许具有最低系统访问级别的用户安全运行该应用程序。 下面的示例假定已添加 <xref:System.Windows.Forms.RichTextBox> 控件的窗体。

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
    > 이 예제에서는 파일이 아직 없는 경우 새 파일을 만듭니다. 如果应用程序需要创建文件，则该应用程序需要为该文件夹创建访问权限。 권한은 액세스 제어 목록을 사용하여 설정됩니다. 如果该文件已存在，则该应用程序只需一个较小的权限。 如果可能，在部署过程中创建文件并只授予对单个文件的读取访问权限，而不是创建对文件夹的访问权限，则更安全。 또한 루트 폴더나 Program Files 폴더보다 사용자 폴더에 데이터를 쓰는 것이 더 안전합니다.

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
