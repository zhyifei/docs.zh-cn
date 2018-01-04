---
title: "如何：在运行时修改图片的大小或位置（Windows 窗体）"
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
- images [Windows Forms], controlling placement in PictureBox control [Windows Forms]
- examples [Windows Forms], PictureBox control
- PictureBox control [Windows Forms], picture size and alignment
- pictures [Windows Forms], controlling placement in PictureBox control [Windows Forms]
ms.assetid: d0b332a3-fae2-4891-957c-dc3e17743326
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e02ea1cbcb1fdd86d182bfba23241acb91c4b54a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="95882-102">如何：在运行时修改图片的大小或位置（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="95882-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="95882-103">如果你使用 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件在窗体中，可以设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到属性：</span><span class="sxs-lookup"><span data-stu-id="95882-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
-   <span data-ttu-id="95882-104">将图片的左上的角的控件的左上角对齐</span><span class="sxs-lookup"><span data-stu-id="95882-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
-   <span data-ttu-id="95882-105">使控件内的图片居中</span><span class="sxs-lookup"><span data-stu-id="95882-105">Center the picture within the control</span></span>  
  
-   <span data-ttu-id="95882-106">调整控件以适应其显示的图片的大小</span><span class="sxs-lookup"><span data-stu-id="95882-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
-   <span data-ttu-id="95882-107">拉伸以适合控件显示的任何图片</span><span class="sxs-lookup"><span data-stu-id="95882-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="95882-108">拉伸图片 （尤其是一个位图格式） 可能导致图像质量丢失。</span><span class="sxs-lookup"><span data-stu-id="95882-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="95882-109">图元文件，它们是在运行时绘制图像的图形说明的列表，可更好适用于拉伸比位图。</span><span class="sxs-lookup"><span data-stu-id="95882-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="95882-110">若要在运行时设置的缩放模式属性</span><span class="sxs-lookup"><span data-stu-id="95882-110">To set the SizeMode property at run time</span></span>  
  
1.  <span data-ttu-id="95882-111">设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到<xref:System.Windows.Forms.PictureBoxSizeMode.Normal>（默认值）、 <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>， <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>，或<xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。</span><span class="sxs-lookup"><span data-stu-id="95882-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="95882-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>意味着图像应置于控件的左上角;如果图像大于控件，其下限和右边缘被剪切。</span><span class="sxs-lookup"><span data-stu-id="95882-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="95882-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>意味着映像控件; 内居中如果图像大于控件，图片的外边缘被剪切。</span><span class="sxs-lookup"><span data-stu-id="95882-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="95882-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>表示控件的大小调整为图像的大小。</span><span class="sxs-lookup"><span data-stu-id="95882-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="95882-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>相反，并表示图像的大小调整到控件的大小。</span><span class="sxs-lookup"><span data-stu-id="95882-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="95882-116">在下面的示例中，设置为的位置的路径是映像的我的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="95882-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="95882-117">此操作后，因为你可以采用大多数计算机运行 Windows 操作系统，将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="95882-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="95882-118">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="95882-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="95882-119">下面的示例假定的窗体具有<xref:System.Windows.Forms.PictureBox>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="95882-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="95882-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="95882-120">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="95882-121">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="95882-121">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="95882-122">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="95882-122">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="95882-123">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="95882-123">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="95882-124">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="95882-124">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
