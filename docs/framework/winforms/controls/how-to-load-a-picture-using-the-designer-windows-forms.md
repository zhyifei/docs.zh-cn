---
title: 如何：使用设计器加载图片 (Windows 窗体)
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: 1d95d5baafa42c7dea40933ba837b684d90b7b2b
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972374"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="5985c-102">如何：使用设计器加载图片 (Windows 窗体)</span><span class="sxs-lookup"><span data-stu-id="5985c-102">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="5985c-103">使用 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件, 可以通过<xref:System.Windows.Forms.PictureBox.Image%2A>将属性设置为有效的图片在设计时在窗体上加载和显示图片。</span><span class="sxs-lookup"><span data-stu-id="5985c-103">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="5985c-104">下表显示了可接受的文件类型。</span><span class="sxs-lookup"><span data-stu-id="5985c-104">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="5985c-105">类型</span><span class="sxs-lookup"><span data-stu-id="5985c-105">Type</span></span>|<span data-ttu-id="5985c-106">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="5985c-106">File name extension</span></span>|
|----------|-------------------------|
|<span data-ttu-id="5985c-107">Bitmap</span><span class="sxs-lookup"><span data-stu-id="5985c-107">Bitmap</span></span>|<span data-ttu-id="5985c-108">.bmp</span><span class="sxs-lookup"><span data-stu-id="5985c-108">.bmp</span></span>|
|<span data-ttu-id="5985c-109">图标</span><span class="sxs-lookup"><span data-stu-id="5985c-109">Icon</span></span>|<span data-ttu-id="5985c-110">.ico</span><span class="sxs-lookup"><span data-stu-id="5985c-110">.ico</span></span>|
|<span data-ttu-id="5985c-111">GIF</span><span class="sxs-lookup"><span data-stu-id="5985c-111">GIF</span></span>|<span data-ttu-id="5985c-112">.gif</span><span class="sxs-lookup"><span data-stu-id="5985c-112">.gif</span></span>|
|<span data-ttu-id="5985c-113">图元文件</span><span class="sxs-lookup"><span data-stu-id="5985c-113">Metafile</span></span>|<span data-ttu-id="5985c-114">.wmf</span><span class="sxs-lookup"><span data-stu-id="5985c-114">.wmf</span></span>|
|<span data-ttu-id="5985c-115">JPEG</span><span class="sxs-lookup"><span data-stu-id="5985c-115">JPEG</span></span>|<span data-ttu-id="5985c-116">.jpg</span><span class="sxs-lookup"><span data-stu-id="5985c-116">.jpg</span></span>|

> [!NOTE]
>  <span data-ttu-id="5985c-117">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="5985c-117">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5985c-118">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="5985c-118">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5985c-119">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="5985c-119">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="5985c-120">在设计时显示图片</span><span class="sxs-lookup"><span data-stu-id="5985c-120">To display a picture at design time</span></span>

1. <span data-ttu-id="5985c-121">在窗体上绘制控件。<xref:System.Windows.Forms.PictureBox></span><span class="sxs-lookup"><span data-stu-id="5985c-121">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="5985c-122">在属性窗口上, 选择 " <xref:System.Windows.Forms.PictureBox.Image%2A>属性", 然后单击省略号按钮以显示 "**打开**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="5985c-122">On the Properties window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then click the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="5985c-123">如果要查找特定的文件类型 (例如 .gif 文件), 请在 "**文件类型**" 框中选择它。</span><span class="sxs-lookup"><span data-stu-id="5985c-123">If you are looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="5985c-124">选择要显示的文件。</span><span class="sxs-lookup"><span data-stu-id="5985c-124">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="5985c-125">在设计时清除图片</span><span class="sxs-lookup"><span data-stu-id="5985c-125">To clear the picture at design time</span></span>

1. <span data-ttu-id="5985c-126">在 "**属性**" 窗口中, <xref:System.Windows.Forms.PictureBox.Image%2A>选择属性, 然后右键单击图像对象名称左侧显示的小缩略图图像。</span><span class="sxs-lookup"><span data-stu-id="5985c-126">On the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property and right-click the small thumbnail image that appears to the left of the name of the image object.</span></span> <span data-ttu-id="5985c-127">选择 "**重置**"。</span><span class="sxs-lookup"><span data-stu-id="5985c-127">Choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5985c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="5985c-128">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="5985c-129">PictureBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="5985c-129">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="5985c-130">如何：在运行时修改图片的大小或位置</span><span class="sxs-lookup"><span data-stu-id="5985c-130">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="5985c-131">如何：在运行时设置图片</span><span class="sxs-lookup"><span data-stu-id="5985c-131">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="5985c-132">PictureBox 控件</span><span class="sxs-lookup"><span data-stu-id="5985c-132">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
