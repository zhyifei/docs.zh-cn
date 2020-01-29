---
title: 设置控件显示的文本
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: eb02cbc3b335b0d5856f786b21d1d202cf444211
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738418"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a>如何：设置 Windows 窗体控件显示的文本

Windows 窗体控件通常会显示一些与控件的主要功能相关的文本。 例如，<xref:System.Windows.Forms.Button> 控件通常会显示一个标题，指示在单击该按钮时要执行的操作。 모든 컨트롤에 대해 <xref:System.Windows.Forms.Control.Text%2A> 속성을 사용하여 텍스트를 설정하거나 반환할 수 있습니다. <xref:System.Windows.Forms.Control.Font%2A> 속성을 사용하여 글꼴을 변경할 수 있습니다.

还可以使用[设计器](#designer)设置文本。

## <a name="programmatic"></a>编程

1. <xref:System.Windows.Forms.Control.Text%2A> 속성을 문자열로 설정합니다.

   若要创建带下划线的访问键，请在将作为访问密钥的字母前包含一个 "与" 符号（&）。

2. <xref:System.Windows.Forms.Control.Font%2A> 속성을 <xref:System.Drawing.Font> 형식의 개체로 설정합니다.

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > 이스케이프 문자를 사용하여 일반적으로 다르게 해석하는 메뉴 항목과 같은 사용자 인터페이스 요소에 특수 문자를 표시할 수 있습니다. 例如，下面的代码行将菜单项的文本设置为 "现在为完全不同的内容 &"：

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a>Designer

1. 在 Visual Studio 的 "**属性**" 窗口中，将控件的 " **Text** " 属性设置为相应的字符串。

   若要创建带下划线的快捷键，请在将作为快捷键的字母前包含 "and" 符（&）。

2. 在 "**属性**" 窗口中，选择 "**字体**" 属性旁边的省略号按钮（![省略号按钮（...](./media/visual-studio-ellipsis-button.png)属性窗口）。

   在 "标准字体" 对话框中，选择所需的字体、字体样式、大小、效果（如删除线或下划线）和脚本。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [방법: Windows Forms 컨트롤에 대한 선택키 만들기](how-to-create-access-keys-for-windows-forms-controls.md)
- [방법: Windows Forms 단추 클릭에 응답](how-to-respond-to-windows-forms-button-clicks.md)
