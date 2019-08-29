---
title: 如何：为控件提供工具箱位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e6da7318ba481af721a9220c8f71af2a18e764a3
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015791"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>如何：为控件提供工具箱位图

如果希望在 Visual Studio 的 "**工具箱**" 中显示控件的特殊图标, 则可以使用<xref:System.Drawing.ToolboxBitmapAttribute>指定特定图像。 此类是一个特性，是一种可以附加到其他类上的特殊类。 有关特性的详细信息, 请参阅的C#[特性概述 (Visual Basic](../../../visual-basic/programming-guide/concepts/attributes/index.md) Visual Basic [C#](../../../csharp/programming-guide/concepts/attributes/index.md) )。

<xref:System.Drawing.ToolboxBitmapAttribute>使用, 可以指定一个字符串, 该字符串指示 16 x 16 像素位图的路径和文件名。 添加到“工具箱”后，此位图显示在对应的控件旁边。 你还可以指定<xref:System.Type>, 在这种情况下, 将加载与该类型关联的位图。 如果同时指定一个<xref:System.Type>和一个字符串, 则控件将在包含<xref:System.Type>参数指定的类型的程序集中搜索具有指定名称的图像资源。

## <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>指定控件的工具箱位图

1. 将添加`Class`到控件的类声明中, 然后将其添加到 visual Basic 的关键字之前, 并将其C#添加到 visual 的类声明之上。 <xref:System.Drawing.ToolboxBitmapAttribute>

    ```vb
    ' Specifies the bitmap associated with the Button type.
    <ToolboxBitmap(GetType(Button))> Class MyControl1
    ' Specifies a bitmap file.
    End Class
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _
       Class MyControl2
    End Class
    ' Specifies a type that indicates the assembly to search, and the name
    ' of an image resource to look for.
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl
    End Class
    ```

    ```csharp
    // Specifies the bitmap associated with the Button type.
    [ToolboxBitmap(typeof(Button))]
    class MyControl1 : UserControl
    {
    }
    // Specifies a bitmap file.
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]
    class MyControl2 : UserControl
    {
    }
    // Specifies a type that indicates the assembly to search, and the name
    // of an image resource to look for.
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]
    class MyControl : UserControl
    {
    }
    ```

2. 重新生成项目。

    > [!NOTE]
    > 对于自动生成的控件和组件，位图不会出现在工具箱中。 若要查看位图，请使用“选择工具箱项”对话框重载控件。 有关详细信息，请参见[演练：用自定义组件](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)自动填充工具箱。

## <a name="see-also"></a>请参阅

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [演练：用自定义组件自动填充工具箱](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [设计时开发 Windows 窗体控件](developing-windows-forms-controls-at-design-time.md)
- [特性概述 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [特性 (C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
