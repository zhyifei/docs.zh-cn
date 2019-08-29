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
ms.openlocfilehash: acc5ee47536772d98fcfe98849335933c24a41d7
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015910"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>如何：在 ComboBox 控件中创建大小可变的文本
此示例演示如何自定义<xref:System.Windows.Forms.ComboBox>控件中的文本绘制。 当某个项满足某个条件时, 它将以较大的字体绘制, 并处于红色状态。

## <a name="example"></a>示例

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

## <a name="compiling-the-code"></a>编译代码
 此示例需要：

- Windows 窗体。

- 一个<xref:System.Windows.Forms.ComboBox>名为`ListBox1`的控件<xref:System.Windows.Forms.ComboBox.Items%2A> , 其属性中包含三项。 在此示例中, 三个项的`"One", Two", and Three"`名称为。 <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>的<xref:System.Windows.Forms.ComboBox.DrawMode%2A> 属性`ComboBox1`必须设置为。

    > [!NOTE]
    > 此方法也适用于<xref:System.Windows.Forms.ListBox>控件, 可以将<xref:System.Windows.Forms.ListBox>替换为<xref:System.Windows.Forms.ComboBox>。

- 对 <xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 命名空间的引用。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [具有内置所有者描述支持的控件](controls-with-built-in-owner-drawing-support.md)
- [ListBox 控件](listbox-control-windows-forms.md)
- [ComboBox 控件](combobox-control-windows-forms.md)
