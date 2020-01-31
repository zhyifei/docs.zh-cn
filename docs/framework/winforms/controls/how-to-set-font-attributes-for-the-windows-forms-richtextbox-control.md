---
title: 为 RichTextBox 控件设置字体特性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
ms.openlocfilehash: f27256c155223df576ee3c42e6bf65270c870b0f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744861"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정
Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件有很多用于设置其显示文本格式的选项。 您可以使用 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 属性使所选字符变为粗体、下划线或斜体。 또한 이 속성을 사용하여 선택한 문자의 크기와 서체를 변경할 수도 있습니다. <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 属性允许您更改所选字符的颜色。  
  
### <a name="to-change-the-appearance-of-characters"></a>문자의 모양을 변경하려면  
  
1. 将 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 属性设置为合适的字体。  
  
     若要使用户能够在应用程序中设置字体系列、字号和字体，通常应使用 <xref:System.Windows.Forms.FontDialog> 组件。 개요는 [FontDialog 구성 요소 개요](fontdialog-component-overview-windows-forms.md)를 참조하세요.  
  
2. 将 <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 属性设置为适当的颜色。  
  
     若要使用户能够在应用程序中设置颜色，通常应使用 <xref:System.Windows.Forms.ColorDialog> 组件。 개요는 [ColorDialog 구성 요소 개요](colordialog-component-overview-windows-forms.md)를 참조하세요.  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    > 이러한 속성은 선택한 텍스트에만 적용되며, 선택한 텍스트가 없으면 삽입 지점의 현재 위치에서 입력한 텍스트에 적용됩니다. 有关以编程方式选择文本的信息，请参阅 <xref:System.Windows.Forms.TextBoxBase.Select%2A>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
