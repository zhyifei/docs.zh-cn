---
title: 如何：设置 Windows 窗体 RichTextBox 控件的字体特性
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
ms.openlocfilehash: a6fe5b30c457fae2d53c946092b214f492fe5e9b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331203"
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a><span data-ttu-id="67d28-102">如何：设置 Windows 窗体 RichTextBox 控件的字体特性</span><span class="sxs-lookup"><span data-stu-id="67d28-102">How to: Set Font Attributes for the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="67d28-103">Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件具有许多选项用于设置所显示的文本的格式。</span><span class="sxs-lookup"><span data-stu-id="67d28-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control has numerous options for formatting the text it displays.</span></span> <span data-ttu-id="67d28-104">您可以使所选的字符粗体、 带下划线或斜体，使用<xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="67d28-104">You can make the selected characters bold, underlined, or italic, using the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property.</span></span> <span data-ttu-id="67d28-105">也可以使用此属性来更改所选字符的大小和字样。</span><span class="sxs-lookup"><span data-stu-id="67d28-105">You can also use this property to change the size and typeface of the selected characters.</span></span> <span data-ttu-id="67d28-106"><xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>属性使您能够更改所选的字符的颜色。</span><span class="sxs-lookup"><span data-stu-id="67d28-106">The <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property enables you to change the selected characters' color.</span></span>  
  
### <a name="to-change-the-appearance-of-characters"></a><span data-ttu-id="67d28-107">更改字符的外观</span><span class="sxs-lookup"><span data-stu-id="67d28-107">To change the appearance of characters</span></span>  
  
1. <span data-ttu-id="67d28-108">设置<xref:System.Windows.Forms.RichTextBox.SelectionFont%2A>属性设置为合适的字体。</span><span class="sxs-lookup"><span data-stu-id="67d28-108">Set the <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> property to an appropriate font.</span></span>  
  
     <span data-ttu-id="67d28-109">若要使用户能够在应用程序中设置字体系列、 大小和字样，通常可以使用<xref:System.Windows.Forms.FontDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="67d28-109">To enable users to set the font family, size, and typeface in an application, you would typically use the <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="67d28-110">有关概述，请参阅 [FontDialog 组件概述](fontdialog-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="67d28-110">For an overview, see [FontDialog Component Overview](fontdialog-component-overview-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="67d28-111">设置<xref:System.Windows.Forms.RichTextBox.SelectionColor%2A>属性设置为适当的颜色。</span><span class="sxs-lookup"><span data-stu-id="67d28-111">Set the <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> property to an appropriate color.</span></span>  
  
     <span data-ttu-id="67d28-112">若要使用户能够在应用程序中设置颜色，通常可以使用<xref:System.Windows.Forms.ColorDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="67d28-112">To enable users to set the color in an application, you would typically use the <xref:System.Windows.Forms.ColorDialog> component.</span></span> <span data-ttu-id="67d28-113">有关概述，请参阅 [ColorDialog 组件概述](colordialog-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="67d28-113">For an overview, see [ColorDialog Component Overview](colordialog-component-overview-windows-forms.md).</span></span>  
  
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
    >  <span data-ttu-id="67d28-114">这些属性只影响所选的文本，如果未选择文本，则只影响当前插入点位置处键入的文本。</span><span class="sxs-lookup"><span data-stu-id="67d28-114">These properties only affect selected text, or, if no text is selected, the text that is typed at the current location of the insertion point.</span></span> <span data-ttu-id="67d28-115">有关以编程方式选择文本的信息，请参阅<xref:System.Windows.Forms.TextBoxBase.Select%2A>。</span><span class="sxs-lookup"><span data-stu-id="67d28-115">For information on selecting text programmatically, see <xref:System.Windows.Forms.TextBoxBase.Select%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d28-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="67d28-116">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="67d28-117">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="67d28-117">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="67d28-118">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="67d28-118">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
