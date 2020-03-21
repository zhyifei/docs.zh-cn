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
# <a name="how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms"></a><span data-ttu-id="c9f12-102">如何：在运行时修改图片的大小或位置（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c9f12-102">How to: Modify the Size or Placement of a Picture at Run Time (Windows Forms)</span></span>
<span data-ttu-id="c9f12-103">如果在窗体上使用 Windows<xref:System.Windows.Forms.PictureBox>窗体控件，则可以将窗体上<xref:System.Windows.Forms.PictureBox.SizeMode%2A>的属性设置为：</span><span class="sxs-lookup"><span data-stu-id="c9f12-103">If you use the Windows Forms <xref:System.Windows.Forms.PictureBox> control on a form, you can set the <xref:System.Windows.Forms.PictureBox.SizeMode%2A> property on it to:</span></span>  
  
- <span data-ttu-id="c9f12-104">将图片的左上角与控件的左上角对齐</span><span class="sxs-lookup"><span data-stu-id="c9f12-104">Align the picture's upper left corner with the control's upper left corner</span></span>  
  
- <span data-ttu-id="c9f12-105">将图片居中</span><span class="sxs-lookup"><span data-stu-id="c9f12-105">Center the picture within the control</span></span>  
  
- <span data-ttu-id="c9f12-106">调整控件的大小以适合显示的图片</span><span class="sxs-lookup"><span data-stu-id="c9f12-106">Adjust the size of the control to fit the picture it displays</span></span>  
  
- <span data-ttu-id="c9f12-107">拉伸它显示的任何图片以适合控件</span><span class="sxs-lookup"><span data-stu-id="c9f12-107">Stretch any picture it displays to fit the control</span></span>  
  
 <span data-ttu-id="c9f12-108">拉伸图片（尤其是位图格式）可能会损失图像质量。</span><span class="sxs-lookup"><span data-stu-id="c9f12-108">Stretching a picture (especially one in bitmap format) can produce a loss in image quality.</span></span> <span data-ttu-id="c9f12-109">元文件是运行时绘制图像的图形说明列表，比位图更适合拉伸。</span><span class="sxs-lookup"><span data-stu-id="c9f12-109">Metafiles, which are lists of graphics instructions for drawing images at run time, are better suited for stretching than bitmaps are.</span></span>  
  
### <a name="to-set-the-sizemode-property-at-run-time"></a><span data-ttu-id="c9f12-110">在运行时设置 SizeMode 属性</span><span class="sxs-lookup"><span data-stu-id="c9f12-110">To set the SizeMode property at run time</span></span>  
  
1. <span data-ttu-id="c9f12-111">设置为<xref:System.Windows.Forms.PictureBox.SizeMode%2A><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>（默认值）、<xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>或<xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>。</span><span class="sxs-lookup"><span data-stu-id="c9f12-111">Set <xref:System.Windows.Forms.PictureBox.SizeMode%2A> to <xref:System.Windows.Forms.PictureBoxSizeMode.Normal> (the default), <xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>, <xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>, or <xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>.</span></span> <span data-ttu-id="c9f12-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal>表示图像放置在控件的左上角;如果图像大于控件，则其下边缘和右边缘将剪切。</span><span class="sxs-lookup"><span data-stu-id="c9f12-112"><xref:System.Windows.Forms.PictureBoxSizeMode.Normal> means that the image is placed in the control's upper-left corner; if the image is larger than the control, its lower and right edges are clipped.</span></span> <span data-ttu-id="c9f12-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage>表示图像居中，在控件中居中;如果图像大于控件，则剪切图片的外边缘。</span><span class="sxs-lookup"><span data-stu-id="c9f12-113"><xref:System.Windows.Forms.PictureBoxSizeMode.CenterImage> means that the image is centered within the control; if the image is larger than the control, the picture's outside edges are clipped.</span></span> <span data-ttu-id="c9f12-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize>表示控件的大小会调整为图像的大小。</span><span class="sxs-lookup"><span data-stu-id="c9f12-114"><xref:System.Windows.Forms.PictureBoxSizeMode.AutoSize> means that the size of the control is adjusted to the size of the image.</span></span> <span data-ttu-id="c9f12-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage>是相反的，表示图像的大小会调整到控件的大小。</span><span class="sxs-lookup"><span data-stu-id="c9f12-115"><xref:System.Windows.Forms.PictureBoxSizeMode.StretchImage> is the reverse, and means that the size of the image is adjusted to the size of the control.</span></span>  
  
     <span data-ttu-id="c9f12-116">在下面的示例中，为图像位置设置的路径是"我的文档"文件夹。</span><span class="sxs-lookup"><span data-stu-id="c9f12-116">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="c9f12-117">此操作已完成，因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="c9f12-117">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="c9f12-118">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="c9f12-118">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="c9f12-119">下面的示例假定已添加控件的<xref:System.Windows.Forms.PictureBox>窗体。</span><span class="sxs-lookup"><span data-stu-id="c9f12-119">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9f12-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9f12-120">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="c9f12-121">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="c9f12-121">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="c9f12-122">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="c9f12-122">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="c9f12-123">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="c9f12-123">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="c9f12-124">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="c9f12-124">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
