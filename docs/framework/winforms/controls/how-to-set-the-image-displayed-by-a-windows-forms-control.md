---
title: 如何：设置 Windows 窗体控件显示的图像
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666191"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>如何：设置 Windows 窗体控件显示的图像

若干 Windows 窗体控件可以显示图像。 这些图像可以是阐明控件用途的图标, 如表示 "保存" 命令的按钮上的 "磁盘" 图标。 此外, 图标还可以是背景图像, 为控件指定所需的外观和行为。

## <a name="programmatic"></a>编程

将控件的`Image`或`BackgroundImage`属性设置为类型<xref:System.Drawing.Image>的对象。 通常, 将使用<xref:System.Drawing.Image.FromFile%2A>方法从文件中加载图像。

在下面的代码示例中, 为图像的位置设置的路径是 "**我的图片**" 文件夹。 大多数运行 Windows 操作系统的计算机都包含此目录。 这还可以使具有最低系统访问级别的用户安全运行该应用程序。 下面的代码示例要求您已具有一个已添加<xref:System.Windows.Forms.PictureBox>控件的窗体。

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a>Designer

1. 在 Visual Studio 的 "**属性**" 窗口中, 选择控件的**Image**或**BackgroundImage**属性, 然后选择省略号 (![Visual Studio](./media/visual-studio-ellipsis-button.png)中的省略号按钮) 以显示**select"资源**" 对话框。

2. 选择要显示的图像。

## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
