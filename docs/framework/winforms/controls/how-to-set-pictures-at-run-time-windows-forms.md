---
title: 如何：在运行时设置图片
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
ms.openlocfilehash: cd599ac7e07b5210f8bcff1ffbc76b3d9ee563d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182117"
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="b61a9-102">如何：在运行时设置图片（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b61a9-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="b61a9-103">您可以以编程方式设置 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件显示的图像。</span><span class="sxs-lookup"><span data-stu-id="b61a9-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="b61a9-104">以编程方式设置图片</span><span class="sxs-lookup"><span data-stu-id="b61a9-104">To set a picture programmatically</span></span>  
  
- <span data-ttu-id="b61a9-105">使用<xref:System.Windows.Forms.PictureBox.Image%2A><xref:System.Drawing.Image.FromFile%2A><xref:System.Drawing.Image>类的方法设置属性。</span><span class="sxs-lookup"><span data-stu-id="b61a9-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="b61a9-106">在下面的示例中，为图像位置设置的路径是"我的文档"文件夹。</span><span class="sxs-lookup"><span data-stu-id="b61a9-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="b61a9-107">此操作已完成，因为您可以假定运行 Windows 操作系统的大多数计算机都将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="b61a9-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="b61a9-108">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="b61a9-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="b61a9-109">下面的示例假定已添加控件的<xref:System.Windows.Forms.PictureBox>窗体。</span><span class="sxs-lookup"><span data-stu-id="b61a9-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
    ```vb  
    Private Sub LoadNewPict()  
       ' You should replace the bold image
       ' in the sample below with an icon of your own choosing.  
       PictureBox1.Image = Image.FromFile _  
       (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Image.gif")  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadNewPict(){  
       // You should replace the bold image
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       pictureBox1.Image = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    }  
    ```  
  
    ```cpp  
    private:  
       void LoadNewPict()  
       {  
          // You should replace the bold image
          // in the sample below with an icon of your own choosing.  
          pictureBox1->Image = Image::FromFile(String::Concat(  
             System::Environment::GetFolderPath(  
             System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
       }  
    ```  
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="b61a9-110">清除图形</span><span class="sxs-lookup"><span data-stu-id="b61a9-110">To clear a graphic</span></span>  
  
- <span data-ttu-id="b61a9-111">首先，释放图像正在使用的内存，然后清除图形。</span><span class="sxs-lookup"><span data-stu-id="b61a9-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="b61a9-112">如果内存管理成为问题，垃圾回收稍后将释放内存。</span><span class="sxs-lookup"><span data-stu-id="b61a9-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
    ```vb  
    If Not (PictureBox1.Image Is Nothing) Then  
       PictureBox1.Image.Dispose()  
       PictureBox1.Image = Nothing  
    End If  
    ```  
  
    ```csharp  
    if (pictureBox1.Image != null)
    {  
       pictureBox1.Image.Dispose();  
       pictureBox1.Image = null;  
    }  
    ```  
  
    ```cpp  
    if (pictureBox1->Image != nullptr)  
    {  
       pictureBox1->Image->Dispose();  
       pictureBox1->Image = nullptr;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="b61a9-113">有关为什么要以这种方式使用<xref:System.Drawing.Image.Dispose%2A>方法的详细信息，请参阅[清理非托管资源](../../../standard/garbage-collection/unmanaged.md)。</span><span class="sxs-lookup"><span data-stu-id="b61a9-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="b61a9-114">即使图形在设计时加载到控件中，此代码也会清除图像。</span><span class="sxs-lookup"><span data-stu-id="b61a9-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61a9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b61a9-115">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b61a9-116">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="b61a9-116">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="b61a9-117">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="b61a9-117">How to: Load a Picture Using the Designer</span></span>](how-to-load-a-picture-using-the-designer-windows-forms.md)
- [<span data-ttu-id="b61a9-118">如何：在运行时修改图片的大小或位置</span><span class="sxs-lookup"><span data-stu-id="b61a9-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="b61a9-119">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="b61a9-119">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
