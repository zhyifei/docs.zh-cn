---
title: 用 ImageList 组件添加或删除图像
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
ms.openlocfilehash: f531003377395bf219775e5ddb48ceb0822ff0ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741498"
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a>방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거
在将 Windows 窗体 <xref:System.Windows.Forms.ImageList> 组件与控件关联之前，通常使用图像填充该组件。 但是，在将图像列表与控件相关联后，可以添加和移除图像。  
  
> [!NOTE]
> 删除图像时，验证任何关联控件的 <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> 属性是否仍然有效。  
  
### <a name="to-add-images-programmatically"></a>以编程方式添加图像  
  
- 使用图像列表的 <xref:System.Windows.Forms.ImageList.Images%2A> 属性的 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 方法。  
  
     在下面的代码示例中，为图像的位置设置的路径是 "**我的文档**" 文件夹。 使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。 选择此位置还允许具有最低系统访问级别的用户更安全地运行应用程序。 下面的代码示例要求您具有一个已添加了 <xref:System.Windows.Forms.ImageList> 控件的窗体。  
  
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
  
### <a name="to-add-images-with-a-key-value"></a>添加具有键值的映像。  
  
- 使用图像列表的 <xref:System.Windows.Forms.ImageList.Images%2A> 属性的 <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> 方法之一，该方法采用键值。  
  
     在下面的代码示例中，为图像的位置设置的路径是 "**我的文档**" 文件夹。 使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机都包含此文件夹。 选择此位置还允许具有最低系统访问级别的用户更安全地运行应用程序。 下面的代码示例要求您具有一个已添加了 <xref:System.Windows.Forms.ImageList> 控件的窗体。  
  
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
  
- 使用 <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> 方法删除单个映像  
  
     、-或-  
  
     使用 <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> 方法可清除图像列表中的所有图像。  
  
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
  
### <a name="to-remove-images-by-key"></a>按键删除映像  
  
- 使用 <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> 方法，按其键删除单个映像。  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a>另请参阅

- [ImageList 구성 요소](imagelist-component-windows-forms.md)
- [ImageList 구성 요소 개요](imagelist-component-overview-windows-forms.md)
- [이미지, 비트맵 및 메타파일](../advanced/images-bitmaps-and-metafiles.md)
