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
ms.locfileid: "33533736"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="e53f8-102">如何：设置 Windows 窗体控件所显示的图像</span><span class="sxs-lookup"><span data-stu-id="e53f8-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="e53f8-103">多个 Windows 窗体控件可以显示图像。</span><span class="sxs-lookup"><span data-stu-id="e53f8-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="e53f8-104">这些映像可以是阐明用途的控件，如按钮表示上的磁盘图标的图标**保存**命令。</span><span class="sxs-lookup"><span data-stu-id="e53f8-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="e53f8-105">或者，图标可以是背景图像的外观和行为所需提供的控制。</span><span class="sxs-lookup"><span data-stu-id="e53f8-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="e53f8-106">若要设置控件所显示的图像</span><span class="sxs-lookup"><span data-stu-id="e53f8-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="e53f8-107">设置控件的`Image`或`BackgroundImage`类型的对象属性<xref:System.Drawing.Image>。</span><span class="sxs-lookup"><span data-stu-id="e53f8-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="e53f8-108">通常情况下，则将会加载映像从文件使用<xref:System.Drawing.Image.FromFile%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e53f8-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="e53f8-109">在下面的代码示例中，路径为设置的映像的位置为**我的图片**文件夹。</span><span class="sxs-lookup"><span data-stu-id="e53f8-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="e53f8-110">运行 Windows 操作系统的大多数计算机将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="e53f8-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="e53f8-111">这也使得具有最少的系统访问级别的用户安全地运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e53f8-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="e53f8-112">下面的代码示例要求你已拥有的窗体具有<xref:System.Windows.Forms.PictureBox>添加控件。</span><span class="sxs-lookup"><span data-stu-id="e53f8-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e53f8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="e53f8-113">See Also</span></span>  
 <xref:System.Drawing.Image.FromFile%2A>  
 <xref:System.Drawing.Image>  
 <xref:System.Windows.Forms.Control.BackgroundImage%2A>
