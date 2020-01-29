---
title: 如何：使用设计器加载图片
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 12b90d561a18fcffaafb9c45b7fa6be6dd060215
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736325"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>如何：使用设计器加载图片（Windows 窗体）

使用 Windows 窗体 <xref:System.Windows.Forms.PictureBox> 控件，可以通过将 <xref:System.Windows.Forms.PictureBox.Image%2A> 属性设置为有效的图片在设计时在窗体上加载和显示图片。 下表显示了可接受的文件类型。

|类型|文件扩展名|
|---|---|
|位图|.bmp|
|图标|.ico|
|GIF|.gif|
|图元文件|.wmf|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>在设计时显示图片

1. 在窗体上绘制 <xref:System.Windows.Forms.PictureBox> 控件。

2. 在 "**属性**" 窗口中，选择 "<xref:System.Windows.Forms.PictureBox.Image%2A>" 属性，然后选择省略号按钮以显示 "**打开**" 对话框。

3. 如果你要查找特定的文件类型（例如 .gif 文件），请在 "**文件类型**" 框中选择它。

4. 选择要显示的文件。

## <a name="to-clear-the-picture-at-design-time"></a>在设计时清除图片

1. 在 "**属性**" 窗口中，选择 "<xref:System.Windows.Forms.PictureBox.Image%2A>" 属性。 右键单击图像对象名称左侧显示的小缩略图图像，然后选择 "**重置**"。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PictureBox>
- [PictureBox 控件概述](picturebox-control-overview-windows-forms.md)
- [如何：在运行时修改图片的大小或位置](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [如何：在运行时设置图片](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 控件](picturebox-control-windows-forms.md)
