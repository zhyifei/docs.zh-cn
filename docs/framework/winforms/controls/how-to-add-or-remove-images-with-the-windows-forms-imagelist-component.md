---
title: "如何：使用 Windows 窗体 ImageList 组件添加或移除图像"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ce13ba3413c13ced7ff9a967e23d87622309feb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-or-remove-images-with-the-windows-forms-imagelist-component"></a><span data-ttu-id="64eaa-102">如何：使用 Windows 窗体 ImageList 组件添加或移除图像</span><span class="sxs-lookup"><span data-stu-id="64eaa-102">How to: Add or Remove Images with the Windows Forms ImageList Component</span></span>
<span data-ttu-id="64eaa-103">Windows 窗体<xref:System.Windows.Forms.ImageList>组件通常填充包含图像之前与控件关联。</span><span class="sxs-lookup"><span data-stu-id="64eaa-103">The Windows Forms <xref:System.Windows.Forms.ImageList> component is typically populated with images before it is associated with a control.</span></span> <span data-ttu-id="64eaa-104">但是，你可以添加和与控件关联的图像列表后，再删除映像。</span><span class="sxs-lookup"><span data-stu-id="64eaa-104">However, you can add and remove images after associating the image list with a control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64eaa-105">当删除映像时，验证<xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>任何关联的控件的属性是否仍有效。</span><span class="sxs-lookup"><span data-stu-id="64eaa-105">When you remove images, verify that the <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> property of any associated controls is still valid.</span></span>  
  
### <a name="to-add-images-programmatically"></a><span data-ttu-id="64eaa-106">以编程方式添加映像</span><span class="sxs-lookup"><span data-stu-id="64eaa-106">To add images programmatically</span></span>  
  
-   <span data-ttu-id="64eaa-107">使用<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>图像列表的方法<xref:System.Windows.Forms.ImageList.Images%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="64eaa-107">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> method of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
     <span data-ttu-id="64eaa-108">在下面的代码示例中，路径为设置的映像的位置为**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="64eaa-108">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="64eaa-109">使用此位置是因为你可以假定正在运行 Windows 操作系统的大多数计算机将包含该文件夹。</span><span class="sxs-lookup"><span data-stu-id="64eaa-109">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="64eaa-110">选择此位置还使得用户可以具有最少的系统的访问级别更多安全地运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="64eaa-110">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="64eaa-111">下面的代码示例要求你拥有的窗体具有<xref:System.Windows.Forms.ImageList>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="64eaa-111">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
### <a name="to-add-images-with-a-key-value"></a><span data-ttu-id="64eaa-112">若要添加具有键值的图像。</span><span class="sxs-lookup"><span data-stu-id="64eaa-112">To add images with a key value.</span></span>  
  
-   <span data-ttu-id="64eaa-113">使用之一<xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A>图像列表的方法<xref:System.Windows.Forms.ImageList.Images%2A>采用键值的属性。</span><span class="sxs-lookup"><span data-stu-id="64eaa-113">Use one of the <xref:System.Windows.Forms.ImageList.ImageCollection.Add%2A> methods of the image list's <xref:System.Windows.Forms.ImageList.Images%2A> property that takes a key value.</span></span>  
  
     <span data-ttu-id="64eaa-114">在下面的代码示例中，路径为设置的映像的位置为**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="64eaa-114">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="64eaa-115">使用此位置是因为你可以假定正在运行 Windows 操作系统的大多数计算机将包含该文件夹。</span><span class="sxs-lookup"><span data-stu-id="64eaa-115">This location is used because you can assume that most computers that are running the Windows operating system will include this folder.</span></span> <span data-ttu-id="64eaa-116">选择此位置还使得用户可以具有最少的系统的访问级别更多安全地运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="64eaa-116">Choosing this location also lets users who have minimal system access levels more safely run the application.</span></span> <span data-ttu-id="64eaa-117">下面的代码示例要求你拥有的窗体具有<xref:System.Windows.Forms.ImageList>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="64eaa-117">The following code example requires that you have a form with an <xref:System.Windows.Forms.ImageList> control already added.</span></span>  
  
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
  
1.  
  
### <a name="to-remove-all-images-programmatically"></a><span data-ttu-id="64eaa-118">以编程方式移除所有映像</span><span class="sxs-lookup"><span data-stu-id="64eaa-118">To remove all images programmatically</span></span>  
  
-   <span data-ttu-id="64eaa-119">使用<xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A>方法来删除单一映像</span><span class="sxs-lookup"><span data-stu-id="64eaa-119">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Remove%2A> method to remove a single image</span></span>  
  
     <span data-ttu-id="64eaa-120">-</span><span class="sxs-lookup"><span data-stu-id="64eaa-120">,-or-</span></span>  
  
     <span data-ttu-id="64eaa-121">使用<xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A>方法来清除图像列表中的所有图像。</span><span class="sxs-lookup"><span data-stu-id="64eaa-121">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.Clear%2A> method to clear all images in the image list.</span></span>  
  
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
  
### <a name="to-remove-images-by-key"></a><span data-ttu-id="64eaa-122">若要通过键移除图像</span><span class="sxs-lookup"><span data-stu-id="64eaa-122">To remove images by key</span></span>  
  
-   <span data-ttu-id="64eaa-123">使用<xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A>方法以通过其键中删除单一映像。</span><span class="sxs-lookup"><span data-stu-id="64eaa-123">Use the <xref:System.Windows.Forms.ImageList.ImageCollection.RemoveByKey%2A> method to remove a single image by its key.</span></span>  
  
    ```vb  
    ' Removes the image named "myPhoto" from the list.  
    ImageList1.Images.RemoveByKey("myPhoto")  
    ```  
  
```csharp  
// Removes the image named "myPhoto" from the list.  
imageList1.Images.RemoveByKey("myPhoto");  
```  
  
## <a name="see-also"></a><span data-ttu-id="64eaa-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64eaa-124">See Also</span></span>  
 [<span data-ttu-id="64eaa-125">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="64eaa-125">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)  
 [<span data-ttu-id="64eaa-126">ImageList 组件概述</span><span class="sxs-lookup"><span data-stu-id="64eaa-126">ImageList Component Overview</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-overview-windows-forms.md)  
 [<span data-ttu-id="64eaa-127">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="64eaa-127">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
