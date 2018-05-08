---
title: 如何：在运行时修改图片的大小或位置（Windows 窗体）
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
ms.openlocfilehash: 9e6e114e0a9d7e5e9c17ba21ef941703cd108784
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a>如何：在运行时修改图片的大小或位置（Windows 窗体）
如果你使用 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件在窗体中，可以设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到属性：  
  
-   将图片的左上的角的控件的左上角对齐  
  
-   使控件内的图片居中  
  
-   调整控件以适应其显示的图片的大小  
  
-   拉伸以适合控件显示的任何图片  
  
 拉伸图片 （尤其是一个位图格式） 可能导致图像质量丢失。 图元文件，它们是在运行时绘制图像的图形说明的列表，可更好适用于拉伸比位图。  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a>若要在运行时设置的缩放模式属性  
  
1.  设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到<xref:System.Windows.Forms.PictureBoxSizeMode.Normal>（默认值）、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>， <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>，或<xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。 <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> 意味着图像应置于控件的左上角;如果图像大于控件，其下限和右边缘被剪切。 <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 意味着映像控件; 内居中如果图像大于控件，图片的外边缘被剪切。 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 表示控件的大小调整为图像的大小。 <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 相反，并表示图像的大小调整到控件的大小。  
  
     在下面的示例中，设置为的位置的路径是映像的我的文档文件夹。 此操作后，因为你可以采用大多数计算机运行 Windows 操作系统，将包含此目录。 这还使得具有最低系统访问级别的用户能够安全运行应用程序。 下面的示例假定的窗体具有<xref:System.Windows.Forms.PictureBox>已添加的控件。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.PictureBox>  
 [如何：使用设计器加载图片](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [PictureBox 控件概述](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [如何：在运行时设置图片](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox 控件](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
