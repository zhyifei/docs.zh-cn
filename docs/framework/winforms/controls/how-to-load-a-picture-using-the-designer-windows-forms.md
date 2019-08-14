---
title: 如何：使用设计器加载图片 (Windows 窗体)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972374"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>如何：使用设计器加载图片 (Windows 窗体)

使用 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件, 可以通过<xref:System.Windows.Forms.PictureBox.Image%2A>将属性设置为有效的图片在设计时在窗体上加载和显示图片。 下表显示了可接受的文件类型。

|类型|文件扩展名|
|----------|-------------------------|
|Bitmap|.bmp|
|图标|.ico|
|GIF|.gif|
|图元文件|.wmf|
|JPEG|.jpg|

> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。

## <a name="to-display-a-picture-at-design-time"></a>在设计时显示图片

1. 在窗体上绘制控件。<xref:System.Windows.Forms.PictureBox>

2. 在属性窗口上, 选择 " <xref:System.Windows.Forms.PictureBox.Image%2A>属性", 然后单击省略号按钮以显示 "**打开**" 对话框。

3. 如果要查找特定的文件类型 (例如 .gif 文件), 请在 "**文件类型**" 框中选择它。

4. 选择要显示的文件。

## <a name="to-clear-the-picture-at-design-time"></a>在设计时清除图片

1. 在 "**属性**" 窗口中, <xref:System.Windows.Forms.PictureBox.Image%2A>选择属性, 然后右键单击图像对象名称左侧显示的小缩略图图像。 选择 "**重置**"。

## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.PictureBox>
- [PictureBox 控件概述](picturebox-control-overview-windows-forms.md)
- [如何：在运行时修改图片的大小或位置](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [如何：在运行时设置图片](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 控件](picturebox-control-windows-forms.md)
