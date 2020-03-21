---
title: 使用图像列表组件添加或删除图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], removing from ImageList component
- images [Windows Forms], storing for controls
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
- images [Windows Forms], displaying with controls
ms.assetid: c5eacc56-f769-4e2e-bfb7-f756620913db
ms.openlocfilehash: e045be7ea9407bc379b0c22282fcd2184ff5db51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182299"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>如何：使用 Windows 窗体 ImageList 组件添加或移除图像
Windows 窗体<xref:System.Windows.Forms.ImageList>组件通常在与控件关联之前填充图像。 但是，您可以将图像列表与控件关联后添加和删除图像。  
  
> [!NOTE]
> 删除图像时，请验证任何关联的<xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>控件的属性是否仍然有效。  
  
### <a name="to-add-images-programmatically"></a>以编程方式添加图像  
  
- 使用<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>图像列表<xref:System.Windows.Forms.ImageList.Images%2A>属性的方法。  
  
     在下面的代码示例中，为图像位置设置的路径是 **"我的文档"** 文件夹。 使用此位置是因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此文件夹。 选择此位置还使具有最小系统访问级别的用户能够更安全地运行应用程序。 以下代码示例要求您具有已添加控件的<xref:System.Windows.Forms.ImageList>窗体。  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    End Sub  
    ```  
  
    ```csharp  
    public void addImage()  
    {  
    // Be sure that you use an appropriate escape sequence (such as the
    // @) when specifying the location of the file.  
       System.Drawing.Image myImage =
         Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
    }  
    ```  
  
    ```cpp  
    public:  
       void addImage()  
       {  
       // Replace the bold image in the following sample
       // with your own icon.  
       // Be sure that you use an appropriate escape sequence (such as
       // \\) when specifying the location of the file.  
          System::Drawing::Image ^ myImage =
             Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
       }  
    ```  
  
### <a name="to-add-images-with-a-key-value"></a>添加具有键值的图像。  
  
- 使用图像列表<xref:System.Windows.Forms.ImageList.Images%2A>属性<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>中采用键值的方法之一。  
  
     在下面的代码示例中，为图像位置设置的路径是 **"我的文档"** 文件夹。 使用此位置是因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此文件夹。 选择此位置还使具有最小系统访问级别的用户能够更安全地运行应用程序。 以下代码示例要求您具有已添加控件的<xref:System.Windows.Forms.ImageList>窗体。  
  
    ```vb  
    Public Sub LoadImage()  
       Dim myImage As System.Drawing.Image = _  
         Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
       ImageList1.Images.Add("myPhoto", myImage)  
    End Sub  
    ```  
  
```csharp  
public void addImage()  
{  
// Be sure that you use an appropriate escape sequence (such as the
// @) when specifying the location of the file.  
   System.Drawing.Image myImage =
     Image.FromFile  
   (System.Environment.GetFolderPath  
   (System.Environment.SpecialFolder.Personal)  
   + @"\Image.gif");  
   imageList1.Images.Add("myPhoto", myImage);  
}  
```  
  
### <a name="to-remove-all-images-programmatically"></a>以编程方式删除所有图像  
  
- 使用<xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>方法删除单个图像  
  
     或-  
  
     使用<xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>方法清除图像列表中的所有图像。  
  
    ```vb  
    ' Removes the first image in the image list  
    ImageList1.Images.Remove(myImage)  
    ' Clears all images in the image list  
    ImageList1.Images.Clear()  
    ```  
  
```csharp  
// Removes the first image in the image list.  
imageList1.Images.Remove(myImage);  
// Clears all images in the image list.  
imageList1.Images.Clear();  
```  
  
### <a name="to-remove-images-by-key"></a>按键删除图像  
  
- 使用<xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>方法按其键删除单个图像。  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>另请参阅

- [ImageList 组件](imagelist-component-windows-forms.md)
- [ImageList 组件概述](imagelist-component-overview-windows-forms.md)
- [图像、位图和图元文件](../advanced/images-bitmaps-and-metafiles.md)
