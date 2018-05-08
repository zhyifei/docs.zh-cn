---
title: 如何：设置 Windows 窗体控件所显示的图像
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
ms.openlocfilehash: 4870f9e2acc48a90e1e2193d514926fedee05f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a>如何：设置 Windows 窗体控件所显示的图像
多个 Windows 窗体控件可以显示图像。 这些映像可以是阐明用途的控件，如按钮表示上的磁盘图标的图标**保存**命令。 或者，图标可以是背景图像的外观和行为所需提供的控制。  
  
### <a name="to-set-the-image-displayed-by-a-control"></a>若要设置控件所显示的图像  
  
1.  设置控件的`Image`或`BackgroundImage`类型的对象属性<xref:System.Drawing.Image>。 通常情况下，则将会加载映像从文件使用<xref:System.Drawing.Image.FromFile%2A>方法。  
  
     在下面的代码示例中，路径为设置的映像的位置为**我的图片**文件夹。 运行 Windows 操作系统的大多数计算机将包含此目录。 这也使得具有最少的系统访问级别的用户安全地运行该应用程序。 下面的代码示例要求你已拥有的窗体具有<xref:System.Windows.Forms.PictureBox>添加控件。  
  
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
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
