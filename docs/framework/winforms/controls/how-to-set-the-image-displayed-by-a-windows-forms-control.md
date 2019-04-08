---
title: 如何：设置 Windows 窗体控件显示的图像
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
ms.openlocfilehash: 031ddcb3b852e75353fed7420735350e79f23df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085085"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="44c27-102">如何：设置 Windows 窗体控件显示的图像</span><span class="sxs-lookup"><span data-stu-id="44c27-102">How to: Set the Image Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="44c27-103">多个 Windows 窗体控件可以显示图像。</span><span class="sxs-lookup"><span data-stu-id="44c27-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="44c27-104">这些映像可以是阐明用途的控件，例如上按钮表示的磁盘图标的图标**保存**命令。</span><span class="sxs-lookup"><span data-stu-id="44c27-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="44c27-105">或者，图标可以是为控件提供的外观和行为所需的背景图像。</span><span class="sxs-lookup"><span data-stu-id="44c27-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>  
  
### <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="44c27-106">若要设置控件所显示的图像</span><span class="sxs-lookup"><span data-stu-id="44c27-106">To set the image displayed by a control</span></span>  
  
1.  <span data-ttu-id="44c27-107">设置控件的`Image`或`BackgroundImage`类型的对象的属性<xref:System.Drawing.Image>。</span><span class="sxs-lookup"><span data-stu-id="44c27-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="44c27-108">通常情况下，你会将图像从文件加载使用<xref:System.Drawing.Image.FromFile%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="44c27-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>  
  
     <span data-ttu-id="44c27-109">在下面的代码示例中，将路径设置的映像的位置是**My Pictures**文件夹。</span><span class="sxs-lookup"><span data-stu-id="44c27-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="44c27-110">大多数运行 Windows 操作系统的计算机将包含此目录。</span><span class="sxs-lookup"><span data-stu-id="44c27-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="44c27-111">这还使具有最少的系统访问级别的用户安全地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="44c27-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="44c27-112">下面的代码示例要求您已有一个具有窗体<xref:System.Windows.Forms.PictureBox>添加控件。</span><span class="sxs-lookup"><span data-stu-id="44c27-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="44c27-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="44c27-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
