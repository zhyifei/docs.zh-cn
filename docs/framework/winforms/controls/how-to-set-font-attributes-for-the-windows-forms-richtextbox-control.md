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
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="2ca83-102">방법: Windows Forms RichTextBox 컨트롤의 글꼴 특성 설정</span><span class="sxs-lookup"><span data-stu-id="2ca83-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="2ca83-103">Windows 窗体 <xref:System.Windows.Forms.RichTextBox> 控件有很多用于设置其显示文本格式的选项。</span><span class="sxs-lookup"><span data-stu-id="2ca83-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="2ca83-104">您可以使用 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 属性使所选字符变为粗体、下划线或斜体。</span><span class="sxs-lookup"><span data-stu-id="2ca83-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="2ca83-105">또한 이 속성을 사용하여 선택한 문자의 크기와 서체를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ca83-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="2ca83-106"><xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 属性允许您更改所选字符的颜色。</span><span class="sxs-lookup"><span data-stu-id="2ca83-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="2ca83-107">문자의 모양을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="2ca83-107">To change the appearance of characters</span></span>  
  
1. <span data-ttu-id="2ca83-108">将 <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> 属性设置为合适的字体。</span><span class="sxs-lookup"><span data-stu-id="2ca83-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="2ca83-109">若要使用户能够在应用程序中设置字体系列、字号和字体，通常应使用 <xref:System.Windows.Forms.FontDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="2ca83-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="2ca83-110">개요는 [FontDialog 구성 요소 개요](fontdialog-component-overview-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ca83-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="2ca83-111">将 <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> 属性设置为适当的颜色。</span><span class="sxs-lookup"><span data-stu-id="2ca83-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="2ca83-112">若要使用户能够在应用程序中设置颜色，通常应使用 <xref:System.Windows.Forms.ColorDialog> 组件。</span><span class="sxs-lookup"><span data-stu-id="2ca83-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="2ca83-113">개요는 [ColorDialog 구성 요소 개요](colordialog-component-overview-windows-forms.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2ca83-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
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
    > <span data-ttu-id="2ca83-114">이러한 속성은 선택한 텍스트에만 적용되며, 선택한 텍스트가 없으면 삽입 지점의 현재 위치에서 입력한 텍스트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ca83-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="2ca83-115">有关以编程方式选择文本的信息，请参阅 <xref:System.Windows.Forms.TextBoxBase.Select%2A>。</span><span class="sxs-lookup"><span data-stu-id="2ca83-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ca83-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ca83-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="2ca83-117">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ca83-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="2ca83-118">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2ca83-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
