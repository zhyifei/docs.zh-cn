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
ms.openlocfilehash: fea813d7b9fe585e35b729b8b64e3a5f414ef76d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141961"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>如何：在运行时修改图片的大小或位置（Windows 窗体）
如果在窗体上使用 Windows<xref:System.Windows.Forms.PictureBox>窗体控件，则可以将窗体上<xref:System.Windows.Forms.PictureBox.SizeMode%2A>的属性设置为：  
  
- 将图片的左上角与控件的左上角对齐  
  
- 将图片居中  
  
- 调整控件的大小以适合显示的图片  
  
- 拉伸它显示的任何图片以适合控件  
  
 拉伸图片（尤其是位图格式）可能会损失图像质量。 元文件是运行时绘制图像的图形说明列表，比位图更适合拉伸。  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>在运行时设置 SizeMode 属性  
  
1. 设置为<xref:System.Windows.Forms.PictureBox.SizeMode%2A><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>（默认值）、<xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>或<xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal>表示图像放置在控件的左上角;如果图像大于控件，则其下边缘和右边缘将剪切。 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>表示图像居中，在控件中居中;如果图像大于控件，则剪切图片的外边缘。 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>表示控件的大小会调整为图像的大小。 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>是相反的，表示图像的大小会调整到控件的大小。  
  
     在下面的示例中，为图像位置设置的路径是"我的文档"文件夹。 此操作已完成，因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。 下面的示例假定已添加控件的<xref:System.Windows.Forms.PictureBox>窗体。  
  
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
