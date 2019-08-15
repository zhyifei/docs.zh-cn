---
title: 如何：设置 Windows 窗体控件显示的图像
ms.date: 03/30/2017
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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037872"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>如何：设置 Windows 窗体控件显示的图像

若干 Windows 窗体控件可以显示图像。 这些图像可以是阐明控件用途的图标, 如表示 "**保存**" 命令的按钮上的 "磁盘" 图标。 此外, 图标还可以是背景图像, 为控件指定所需的外观和行为。

## <a name="to-set-the-image-displayed-by-a-control"></a>设置控件显示的图像

1. 将控件的`Image`或`BackgroundImage`属性设置为类型<xref:System.Drawing.Image>的对象。 通常, 你将使用<xref:System.Drawing.Image.FromFile%2A>方法从文件中加载图像。

     在下面的代码示例中, 为图像的位置设置的路径是 "**我的图片**" 文件夹。 大多数运行 Windows 操作系统的计算机都将包括此目录。 这还可以使具有最低系统访问级别的用户安全运行该应用程序。 下面的代码示例要求您已具有一个已添加<xref:System.Windows.Forms.PictureBox>控件的窗体。

    ```vb
    ' Replace the image named below
    ' with an icon of your own choosing.
    PictureBox1.Image = Image.FromFile _
       (System.Environment.GetFolderPath _
       (System.Environment.SpecialFolder.MyPictures) _
       & "\Image.gif")
    ```

    ```csharp
    // Replace the image named below
    // with an icon of your own choosing.
    // Note the escape character used (@) when specifying the path.
    pictureBox1.Image = Image.FromFile
       (System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.MyPictures)
       + @"\Image.gif");
    ```

    ```cpp
    // Replace the image named below
    // with an icon of your own choosing.
    pictureBox1->Image = Image::FromFile(String::Concat
       (System::Environment::GetFolderPath
       (System::Environment::SpecialFolder::MyPictures),
       "\\Image.gif"));
    ```

## <a name="see-also"></a>请参阅

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
