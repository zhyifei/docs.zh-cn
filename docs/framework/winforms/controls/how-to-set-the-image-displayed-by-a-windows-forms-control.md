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
ms.openlocfilehash: 99bde4fac7b3057358c7e6a8550efdb4cc351eb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037872"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="f6b46-102">如何：设置 Windows 窗体控件显示的图像</span><span class="sxs-lookup"><span data-stu-id="f6b46-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="f6b46-103">若干 Windows 窗体控件可以显示图像。</span><span class="sxs-lookup"><span data-stu-id="f6b46-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="f6b46-104">这些图像可以是阐明控件用途的图标, 如表示 "**保存**" 命令的按钮上的 "磁盘" 图标。</span><span class="sxs-lookup"><span data-stu-id="f6b46-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the **Save** command.</span></span> <span data-ttu-id="f6b46-105">此外, 图标还可以是背景图像, 为控件指定所需的外观和行为。</span><span class="sxs-lookup"><span data-stu-id="f6b46-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="to-set-the-image-displayed-by-a-control"></a><span data-ttu-id="f6b46-106">设置控件显示的图像</span><span class="sxs-lookup"><span data-stu-id="f6b46-106">To set the image displayed by a control</span></span>

1. <span data-ttu-id="f6b46-107">将控件的`Image`或`BackgroundImage`属性设置为类型<xref:System.Drawing.Image>的对象。</span><span class="sxs-lookup"><span data-stu-id="f6b46-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f6b46-108">通常, 你将使用<xref:System.Drawing.Image.FromFile%2A>方法从文件中加载图像。</span><span class="sxs-lookup"><span data-stu-id="f6b46-108">Generally, you will be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

     <span data-ttu-id="f6b46-109">在下面的代码示例中, 为图像的位置设置的路径是 "**我的图片**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f6b46-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="f6b46-110">大多数运行 Windows 操作系统的计算机都将包括此目录。</span><span class="sxs-lookup"><span data-stu-id="f6b46-110">Most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="f6b46-111">这还可以使具有最低系统访问级别的用户安全运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6b46-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="f6b46-112">下面的代码示例要求您已具有一个已添加<xref:System.Windows.Forms.PictureBox>控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="f6b46-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f6b46-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b46-113">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
