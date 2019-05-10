---
title: 如何：在运行时 （Windows 窗体） 中修改的大小或位置的图片
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
ms.openlocfilehash: 695abf51870ef9164e4543a91b3183e801eee55f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649257"
---
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="a2e3d-102">如何：在运行时 （Windows 窗体） 中修改的大小或位置的图片</span><span class="sxs-lookup"><span data-stu-id="a2e3d-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="a2e3d-103">如果使用 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件在窗体上可以设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到其上的属性：</span><span class="sxs-lookup"><span data-stu-id="a2e3d-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="a2e3d-104">将图片的左上的角的控件的左上角对齐</span><span class="sxs-lookup"><span data-stu-id="a2e3d-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="a2e3d-105">使图片在控件内居中</span><span class="sxs-lookup"><span data-stu-id="a2e3d-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="a2e3d-106">调整控件以适合其显示的图片的大小</span><span class="sxs-lookup"><span data-stu-id="a2e3d-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="a2e3d-107">拉伸以适合控件显示的任何图片</span><span class="sxs-lookup"><span data-stu-id="a2e3d-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="a2e3d-108">拉伸图片 （尤其是一个位图格式） 可能导致丢失在图像质量。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="a2e3d-109">图元文件，这是一系列有关在运行时绘制图像的图形说明的都更好地适合拉伸比位图。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="a2e3d-110">若要在运行时设置的缩放模式属性</span><span class="sxs-lookup"><span data-stu-id="a2e3d-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="a2e3d-111">设置<xref:System.Windows.Forms.PictureBox.SizeMode%2A>到<xref:System.Windows.Forms.PictureBoxSizeMode.Normal>（默认值）， <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>， <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>，或<xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="a2e3d-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> 映像是放置控件的左上角;如果图像大于该控件，将剪切其较低和右边缘。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="a2e3d-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> 表示该映像在控件中; 中居中如果图像大于该控件，将剪切图片的外边缘。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="a2e3d-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> 表示控件的大小调整为图像的大小。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="a2e3d-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> 相反，并表示图像的大小调整为该控件的大小。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="a2e3d-116">在下面的示例中，设置的位置的路径是映像的 My Documents 文件夹。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="a2e3d-117">此操作后，因为您可以假定大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="a2e3d-118">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="a2e3d-119">下面的示例假定窗体具有<xref:System.Windows.Forms.PictureBox>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="a2e3d-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2e3d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e3d-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="a2e3d-121">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="a2e3d-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="a2e3d-122">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="a2e3d-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="a2e3d-123">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="a2e3d-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="a2e3d-124">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="a2e3d-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
