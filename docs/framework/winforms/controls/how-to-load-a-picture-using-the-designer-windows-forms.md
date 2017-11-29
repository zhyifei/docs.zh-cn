---
title: "如何：使用设计器加载图片（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9049bf5f9467401bff098459b8f5ed55c1ee1975
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="c2b2f-102">如何：使用设计器加载图片（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="c2b2f-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>
<span data-ttu-id="c2b2f-103">在 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件，可以加载并将图片窗体上显示在设计时，通过设置<xref:System.Windows.Forms.PictureBox.Image%2A>属性设置为有效的图片。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="c2b2f-104">下表显示可接受文件类型。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-104">The following table shows the acceptable file types.</span></span>  
  
|<span data-ttu-id="c2b2f-105">类型</span><span class="sxs-lookup"><span data-stu-id="c2b2f-105">Type</span></span>|<span data-ttu-id="c2b2f-106">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="c2b2f-106">File name extension</span></span>|  
|----------|-------------------------|  
|<span data-ttu-id="c2b2f-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="c2b2f-107">Bitmap</span></span>|<span data-ttu-id="c2b2f-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="c2b2f-108">.bmp</span></span>|  
|<span data-ttu-id="c2b2f-109">图标</span><span class="sxs-lookup"><span data-stu-id="c2b2f-109">Icon</span></span>|<span data-ttu-id="c2b2f-110">.ico</span><span class="sxs-lookup"><span data-stu-id="c2b2f-110">.ico</span></span>|  
|<span data-ttu-id="c2b2f-111">GIF</span><span class="sxs-lookup"><span data-stu-id="c2b2f-111">GIF</span></span>|<span data-ttu-id="c2b2f-112">.gif</span><span class="sxs-lookup"><span data-stu-id="c2b2f-112">.gif</span></span>|  
|<span data-ttu-id="c2b2f-113">图元文件</span><span class="sxs-lookup"><span data-stu-id="c2b2f-113">Metafile</span></span>|<span data-ttu-id="c2b2f-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="c2b2f-114">.wmf</span></span>|  
|<span data-ttu-id="c2b2f-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="c2b2f-115">JPEG</span></span>|<span data-ttu-id="c2b2f-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="c2b2f-116">.jpg</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c2b2f-117">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c2b2f-118">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c2b2f-119">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-119">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="c2b2f-120">要在设计时显示的图片</span><span class="sxs-lookup"><span data-stu-id="c2b2f-120">To display a picture at design time</span></span>  
  
1.  <span data-ttu-id="c2b2f-121">绘制<xref:System.Windows.Forms.PictureBox>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>  
  
2.  <span data-ttu-id="c2b2f-122">在属性窗口中，选择<xref:System.Windows.Forms.PictureBox.Image%2A>属性，然后单击省略号按钮以显示**打开**对话框。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>  
  
3.  <span data-ttu-id="c2b2f-123">如果你要查找特定文件类型 （例如，.gif 文件），选择在**类型的文件**框。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>  
  
4.  <span data-ttu-id="c2b2f-124">选择你想要显示的文件。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-124">Select the file you want to display.</span></span>  
  
### <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="c2b2f-125">若要在设计时清除图片</span><span class="sxs-lookup"><span data-stu-id="c2b2f-125">To clear the picture at design time</span></span>  
  
1.  <span data-ttu-id="c2b2f-126">上**属性**窗口中，选择<xref:System.Windows.Forms.PictureBox.Image%2A>属性并右键单击显示的图像对象的名称左侧的小缩略图。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="c2b2f-127">选择**重置**。</span><span class="sxs-lookup"><span data-stu-id="c2b2f-127">Choose **Reset**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b2f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2b2f-128">See Also</span></span>  
 <xref:System.Windows.Forms.PictureBox>  
 [<span data-ttu-id="c2b2f-129">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="c2b2f-129">PictureBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [<span data-ttu-id="c2b2f-130">如何：在运行时修改图片的大小或位置</span><span class="sxs-lookup"><span data-stu-id="c2b2f-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [<span data-ttu-id="c2b2f-131">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="c2b2f-131">How to: Set Pictures at Run Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [<span data-ttu-id="c2b2f-132">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="c2b2f-132">PictureBox Control</span></span>](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
