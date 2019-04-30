---
title: 如何：在 ComboBox 控件中创建大小可变的文本
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: 9155893b3d47707e0e55ee33e30d7998654f9e93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61965488"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a><span data-ttu-id="54a44-102">如何：在 ComboBox 控件中创建大小可变的文本</span><span class="sxs-lookup"><span data-stu-id="54a44-102">How to: Create Variable Sized Text in a ComboBox Control</span></span>
<span data-ttu-id="54a44-103">此示例演示自定义绘图中的文本<xref:System.Windows.Forms.ComboBox>控件。</span><span class="sxs-lookup"><span data-stu-id="54a44-103">This example demonstrates custom drawing of text in a <xref:System.Windows.Forms.ComboBox> control.</span></span> <span data-ttu-id="54a44-104">在项符合特定条件时，它是绘制中的较大图标，打开红色。</span><span class="sxs-lookup"><span data-stu-id="54a44-104">When an item meets a certain criteria, it is drawn in a larger font and turned red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54a44-105">示例</span><span class="sxs-lookup"><span data-stu-id="54a44-105">Example</span></span>  
  
```vb  
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
    Dim siText As SizeF  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _  
lFont)  
    Else  
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)  
    End If  
  
    e.ItemHeight = siText.Height  
    e.ItemWidth = siText.Width  
End Sub  
  
Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _  
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem  
    Dim g As Graphics = e.Graphics  
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)  
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)  
  
    If ComboBox1.Items().Item(e.Index) = "Two" Then  
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _  
e.Bounds.X, e.Bounds.Y)  
    Else  
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)  
    End If  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54a44-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="54a44-106">Compiling the Code</span></span>  
 <span data-ttu-id="54a44-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="54a44-107">This example requires:</span></span>  
  
- <span data-ttu-id="54a44-108">Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="54a44-108">A Windows form.</span></span>  
  
- <span data-ttu-id="54a44-109">一个<xref:System.Windows.Forms.ComboBox>名为控件`ListBox1`与中的三个项<xref:System.Windows.Forms.ComboBox.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="54a44-109">A <xref:System.Windows.Forms.ComboBox> control named `ListBox1` with three items in the <xref:System.Windows.Forms.ComboBox.Items%2A> property.</span></span> <span data-ttu-id="54a44-110">在此示例中，三个项名为`"One", Two", and Three"`。</span><span class="sxs-lookup"><span data-stu-id="54a44-110">In this example, the three items are named `"One", Two", and Three"`.</span></span> <span data-ttu-id="54a44-111"><xref:System.Windows.Forms.ComboBox.DrawMode%2A>的属性`ComboBox1`必须设置为<xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>。</span><span class="sxs-lookup"><span data-stu-id="54a44-111">The <xref:System.Windows.Forms.ComboBox.DrawMode%2A> property of `ComboBox1` must be set to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="54a44-112">此方法也是适用于<xref:System.Windows.Forms.ListBox>控件，可以替换<xref:System.Windows.Forms.ListBox>为<xref:System.Windows.Forms.ComboBox>。</span><span class="sxs-lookup"><span data-stu-id="54a44-112">This technique is also applicable to the <xref:System.Windows.Forms.ListBox> control — you can substitute a <xref:System.Windows.Forms.ListBox> for the <xref:System.Windows.Forms.ComboBox>.</span></span>  
  
- <span data-ttu-id="54a44-113">对 <xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="54a44-113">References to the <xref:System.Windows.Forms?displayProperty=nameWithType> and <xref:System.Drawing?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54a44-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="54a44-114">See also</span></span>

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [<span data-ttu-id="54a44-115">具有内置所有者描述支持的控件</span><span class="sxs-lookup"><span data-stu-id="54a44-115">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="54a44-116">ListBox 控件</span><span class="sxs-lookup"><span data-stu-id="54a44-116">ListBox Control</span></span>](listbox-control-windows-forms.md)
- [<span data-ttu-id="54a44-117">ComboBox 控件</span><span class="sxs-lookup"><span data-stu-id="54a44-117">ComboBox Control</span></span>](combobox-control-windows-forms.md)
