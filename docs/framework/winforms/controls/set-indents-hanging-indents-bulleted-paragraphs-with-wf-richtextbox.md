---
title: 通过 RichTextBox 控件设置缩进、悬挂缩进和带项目符号的段落
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], setting indents
- .rtf files [Windows Forms], formatting in RichTextBox control
- examples [Windows Forms], text boxes
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting indents and bullets
- text boxes [Windows Forms], bullets
ms.assetid: abfb40e6-5642-4691-8ec1-9d9ae91688dc
ms.openlocfilehash: 4dcd5691f328eac6d94675c50ed41a7d7cc36596
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743016"
---
# <a name="how-to-set-indents-hanging-indents-and-bulleted-paragraphs-with-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤을 사용하여 들여쓰기, 내어쓰기 및 글머리 기호 단락 설정
Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件有很多用于设置其显示文本格式的选项。 通过设置 "<xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>" 属性，可以将所选段落设置为项目符号列表格式。 你还可以使用 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A>、<xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A>和 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 属性设置段落的缩进量（相对于控件的左边缘和右边缘以及其他文本行的左边缘）。  
  
### <a name="to-format-a-paragraph-as-a-bulleted-list"></a>단락의 서식을 글머리 기호 목록으로 지정하려면  
  
1. <xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A> 속성을 `true`으로 설정합니다.  
  
    ```vb  
    RichTextBox1.SelectionBullet = True  
    ```  
  
    ```csharp  
    richTextBox1.SelectionBullet = true;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionBullet = true;  
    ```  
  
### <a name="to-indent-a-paragraph"></a>단락을 들여쓰려면  
  
1. 将 <xref:System.Windows.Forms.RichTextBox.SelectionIndent%2A> 属性设置为一个整数，该整数表示控件左边缘与文本左边缘之间的距离（以像素为单位）。  
  
2. 将 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 属性设置为一个整数，该整数表示段落中第一行文本的左边缘与同一段落中后续行的左边缘之间的距离（以像素为单位）。 <xref:System.Windows.Forms.RichTextBox.SelectionHangingIndent%2A> 属性的值仅适用于在第一行下换行的段落中的行。  
  
3. 将 <xref:System.Windows.Forms.RichTextBox.SelectionRightIndent%2A> 属性设置为一个整数，该整数表示控件的右边缘与该文本的右边缘之间的距离（以像素为单位）。  
  
    ```vb  
    RichTextBox1.SelectionIndent = 8  
    RichTextBox1.SelectionHangingIndent = 3  
    RichTextBox1.SelectionRightIndent = 12  
    ```  
  
    ```csharp  
    richTextBox1.SelectionIndent = 8;  
    richTextBox1.SelectionHangingIndent = 3;  
    richTextBox1.SelectionRightIndent = 12;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionIndent = 8;  
    richTextBox1->SelectionHangingIndent = 3;  
    richTextBox1->SelectionRightIndent = 12;  
    ```  
  
    > [!NOTE]
    > 이러한 모든 속성은 선택한 텍스트가 포함된 단락에 적용되며, 현재 삽입 지점 이후로 입력된 텍스트에도 적용됩니다. 예를 들어 사용자가 단락 내의 단어를 선택한 다음 들여쓰기를 조정하면, 이 단어가 포함된 전체 단락뿐만 아니라 선택한 단락 이후에 입력되는 모든 단락에도 새 설정이 적용됩니다. 有关以编程方式选择文本的信息，请参阅 <xref:System.Windows.Forms.TextBoxBase.Select%2A>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
