---
title: 如何：在运行时修改图片的大小或位置
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
ms.openlocfilehash: 9bb094ce0b7945f23a2e9b8614e56c9492d5f832
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736035"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>如何：在运行时修改图片的大小或位置（Windows 窗体）
如果在窗体上使用 Windows 窗体 <xref:System.Windows.Forms.PictureBox> 控件，则可以将其上的 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 属性设置为：  
  
- 将图片的左上角与控件的左上角对齐  
  
- 使图片在控件内居中  
  
- 调整控件的大小以适应它所显示的图片  
  
- 伸展显示的任何图片以适应控件  
  
 拉伸图片（尤其是位图格式的图片）可能会导致图像质量损失。 图元文件是在运行时绘制图像的图形说明的列表，更适合于拉伸而不是位图。  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>在运行时设置 Picturebox1.sizemode 属性  
  
1. 将 <xref:System.Windows.Forms.PictureBox.SizeMode%2A> 设置为 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> （默认值）、<xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>、<xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>或 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> 表示将图像放置在控件的左上角;如果图像大于控件，将剪裁其下边缘和右边缘。 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 表示图像在控件内居中;如果图像大于控件，则裁剪图片的外边缘。 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 表示控件的大小调整为图像的大小。 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 是反向的，表示将图像大小调整为控件的大小。  
  
     在下面的示例中，为图像的位置设置的路径是 "我的文档" 文件夹。 这样做是因为您可以假定大多数运行 Windows 操作系统的计算机都包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。 下面的示例假定已添加 <xref:System.Windows.Forms.PictureBox> 控件的窗体。  
  
    ```vb  
    Private Sub StretchPic()  
       ' Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage  
       ' Load the picture into the control.  
       ' You should replace the bold image   
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void StretchPic(){  
       // Stretch the picture to fit the control.  
       PictureBox1.SizeMode = PictureBoxSizeMode.StretchImage;  
       // Load the picture into the control.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\Image.gif")  
    }  
    ```  
  
    ```cpp  
    private:  
       void StretchPic()  
       {  
          // Stretch the picture to fit the control.  
          pictureBox1->SizeMode = PictureBoxSizeMode::StretchImage;  
          // Load the picture into the control.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PictureBox>
- [如何：使用设计器加载图片](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [PictureBox 控件概述](picturebox-control-overview-windows-forms.md)
- [如何：在运行时设置图片](how-to-set-pictures-at-run-time-windows-forms.md)
- [PictureBox 控件](picturebox-control-windows-forms.md)
