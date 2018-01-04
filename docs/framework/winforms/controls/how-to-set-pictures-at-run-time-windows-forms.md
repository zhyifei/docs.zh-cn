---
title: "如何：在运行时设置图片（Windows 窗体）"
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
- pictures [Windows Forms], setting display
- examples [Windows Forms], PictureBox control
- bitmaps [Windows Forms], displaying in PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding images
- images [Windows Forms], adding with PictureBox control [Windows Forms]
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 18ca41d0-68a5-4660-985e-a6c1fbc01d76
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fd0e990b494bc0b7a3008f211aa6ded9e04d732
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-pictures-at-run-time-windows-forms"></a><span data-ttu-id="31672-102">如何：在运行时设置图片（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="31672-102">How to: Set Pictures at Run Time (Windows Forms)</span></span>
<span data-ttu-id="31672-103">你可以以编程方式设置 Windows 窗体显示的图像<xref:System.Windows.Forms.PictureBox>控件。</span><span class="sxs-lookup"><span data-stu-id="31672-103">You can programmatically set the image displayed by a Windows Forms <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-set-a-picture-programmatically"></a><span data-ttu-id="31672-104">以编程方式设置图片</span><span class="sxs-lookup"><span data-stu-id="31672-104">To set a picture programmatically</span></span>  
  
-   <span data-ttu-id="31672-105">设置<xref:System.Windows.Forms.PictureBox.Image%2A>属性使用<xref:System.Drawing.Image.FromFile%2A>方法<xref:System.Drawing.Image>类。</span><span class="sxs-lookup"><span data-stu-id="31672-105">Set the <xref:System.Windows.Forms.PictureBox.Image%2A> property using the <xref:System.Drawing.Image.FromFile%2A> method of the <xref:System.Drawing.Image> class.</span></span>  
  
     <span data-ttu-id="31672-106">在下面的示例中，设置为的位置的路径是映像的我的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="31672-106">In the example below, the path set for the location of the image is the My Documents folder.</span></span> <span data-ttu-id="31672-107">此操作后，因为你可以采用大多数计算机运行 Windows 操作系统，将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="31672-107">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="31672-108">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="31672-108">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="31672-109">下面的示例假定的窗体具有<xref:System.Windows.Forms.PictureBox>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="31672-109">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
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
  
### <a name="to-clear-a-graphic"></a><span data-ttu-id="31672-110">若要清除图形</span><span class="sxs-lookup"><span data-stu-id="31672-110">To clear a graphic</span></span>  
  
-   <span data-ttu-id="31672-111">首先，释放正在使用的映像的内存，然后清除该图形。</span><span class="sxs-lookup"><span data-stu-id="31672-111">First, release the memory being used by the image, and then clear the graphic.</span></span> <span data-ttu-id="31672-112">垃圾回收将释放的内存更高版本如果内存管理将成为问题。</span><span class="sxs-lookup"><span data-stu-id="31672-112">Garbage collection will free up the memory later if memory management becomes a problem.</span></span>  
  
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
    >  <span data-ttu-id="31672-113">有关详细信息为何应使用<xref:System.Drawing.Image.Dispose%2A>方法以这种方式，请参阅[清洗向上非托管资源](../../../../docs/standard/garbage-collection/unmanaged.md)。</span><span class="sxs-lookup"><span data-stu-id="31672-113">For more information on why you should use the <xref:System.Drawing.Image.Dispose%2A> method in this way, see [Cleaning Up Unmanaged Resources](../../../../docs/standard/garbage-collection/unmanaged.md).</span></span>  
  
     <span data-ttu-id="31672-114">此代码将清除该映像，即使图形已在设计时加载到控件。</span><span class="sxs-lookup"><span data-stu-id="31672-114">This code will clear the image even if a graphic was loaded into the control at design time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31672-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="31672-115">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 <xref:System.Drawing.Image.FromFile%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="31672-116">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="31672-116">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="31672-117">如何：使用设计器加载图片</span><span class="sxs-lookup"><span data-stu-id="31672-117">How to: Load a Picture Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-load-a-picture-using-the-designer-windows-forms.md)  
 [<span data-ttu-id="31672-118">如何：在运行时修改图片的大小或位置</span><span class="sxs-lookup"><span data-stu-id="31672-118">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="31672-119">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="31672-119">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
