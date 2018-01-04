---
title: "如何：读取图像元数据"
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
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b610e499ff980d2e705ad855ae98c1d54ff412e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="0a1d2-102">如何：读取图像元数据</span><span class="sxs-lookup"><span data-stu-id="0a1d2-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="0a1d2-103">某些图像文件包含您可以读取以确定图像的功能的元数据。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="0a1d2-104">例如，数码相片可能包含您可以读取以确定的品牌和型号的照相机用于捕获映像的元数据。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="0a1d2-105">与[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，您可以读取现有的元数据，并且你还可以向图像文件写入新的元数据。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-105">With [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="0a1d2-106">将存储的元数据的单独片<xref:System.Drawing.Imaging.PropertyItem>对象。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-106"> stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="0a1d2-107">你可以阅读<xref:System.Drawing.Image.PropertyItems%2A>属性<xref:System.Drawing.Image>要从文件中检索所有元数据对象。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="0a1d2-108"><xref:System.Drawing.Image.PropertyItems%2A>属性返回的数组<xref:System.Drawing.Imaging.PropertyItem>对象。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="0a1d2-109">A<xref:System.Drawing.Imaging.PropertyItem>对象具有以下四个属性： `Id`， `Value`， `Len`，和`Type`。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="0a1d2-110">Id</span><span class="sxs-lookup"><span data-stu-id="0a1d2-110">Id</span></span>  
 <span data-ttu-id="0a1d2-111">一个标识元数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="0a1d2-112">可以分配给某些值<xref:System.Drawing.Imaging.PropertyItem.Id%2A>以下表所示。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="0a1d2-113">十六进制值</span><span class="sxs-lookup"><span data-stu-id="0a1d2-113">Hexadecimal value</span></span>|<span data-ttu-id="0a1d2-114">描述</span><span class="sxs-lookup"><span data-stu-id="0a1d2-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="0a1d2-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="0a1d2-115">0x0320</span></span><br /><br /> <span data-ttu-id="0a1d2-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="0a1d2-116">0x010F</span></span><br /><br /> <span data-ttu-id="0a1d2-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="0a1d2-117">0x0110</span></span><br /><br /> <span data-ttu-id="0a1d2-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="0a1d2-118">0x9003</span></span><br /><br /> <span data-ttu-id="0a1d2-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="0a1d2-119">0x829A</span></span><br /><br /> <span data-ttu-id="0a1d2-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="0a1d2-120">0x5090</span></span><br /><br /> <span data-ttu-id="0a1d2-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="0a1d2-121">0x5091</span></span>|<span data-ttu-id="0a1d2-122">映像标题</span><span class="sxs-lookup"><span data-stu-id="0a1d2-122">Image title</span></span><br /><br /> <span data-ttu-id="0a1d2-123">设备制造商</span><span class="sxs-lookup"><span data-stu-id="0a1d2-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="0a1d2-124">设备型号</span><span class="sxs-lookup"><span data-stu-id="0a1d2-124">Equipment model</span></span><br /><br /> <span data-ttu-id="0a1d2-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="0a1d2-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="0a1d2-126">Exif 暴露时间</span><span class="sxs-lookup"><span data-stu-id="0a1d2-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="0a1d2-127">亮度表</span><span class="sxs-lookup"><span data-stu-id="0a1d2-127">Luminance table</span></span><br /><br /> <span data-ttu-id="0a1d2-128">色度表</span><span class="sxs-lookup"><span data-stu-id="0a1d2-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="0a1d2-129">“值”</span><span class="sxs-lookup"><span data-stu-id="0a1d2-129">Value</span></span>  
 <span data-ttu-id="0a1d2-130">值的数组。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-130">An array of values.</span></span> <span data-ttu-id="0a1d2-131">值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="0a1d2-132">Len</span><span class="sxs-lookup"><span data-stu-id="0a1d2-132">Len</span></span>  
 <span data-ttu-id="0a1d2-133">指向的值的数组的长度 （以字节为单位）<xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="0a1d2-134">类型</span><span class="sxs-lookup"><span data-stu-id="0a1d2-134">Type</span></span>  
 <span data-ttu-id="0a1d2-135">指向数组中的值的数据类型`Value`属性。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="0a1d2-136">格式由`Type`下表列出了属性值</span><span class="sxs-lookup"><span data-stu-id="0a1d2-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="0a1d2-137">数字值</span><span class="sxs-lookup"><span data-stu-id="0a1d2-137">Numeric value</span></span>|<span data-ttu-id="0a1d2-138">描述</span><span class="sxs-lookup"><span data-stu-id="0a1d2-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="0a1d2-139">1</span><span class="sxs-lookup"><span data-stu-id="0a1d2-139">1</span></span>|<span data-ttu-id="0a1d2-140">一个 `Byte`</span><span class="sxs-lookup"><span data-stu-id="0a1d2-140">A `Byte`</span></span>|  
|<span data-ttu-id="0a1d2-141">2</span><span class="sxs-lookup"><span data-stu-id="0a1d2-141">2</span></span>|<span data-ttu-id="0a1d2-142">数组`Byte`为 ASCII 编码的对象</span><span class="sxs-lookup"><span data-stu-id="0a1d2-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="0a1d2-143">3</span><span class="sxs-lookup"><span data-stu-id="0a1d2-143">3</span></span>|<span data-ttu-id="0a1d2-144">16 位整数</span><span class="sxs-lookup"><span data-stu-id="0a1d2-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="0a1d2-145">4</span><span class="sxs-lookup"><span data-stu-id="0a1d2-145">4</span></span>|<span data-ttu-id="0a1d2-146">一个 32 位整数</span><span class="sxs-lookup"><span data-stu-id="0a1d2-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="0a1d2-147">5</span><span class="sxs-lookup"><span data-stu-id="0a1d2-147">5</span></span>|<span data-ttu-id="0a1d2-148">两个数组`Byte`对象，后者表示有理数</span><span class="sxs-lookup"><span data-stu-id="0a1d2-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="0a1d2-149">6</span><span class="sxs-lookup"><span data-stu-id="0a1d2-149">6</span></span>|<span data-ttu-id="0a1d2-150">未使用</span><span class="sxs-lookup"><span data-stu-id="0a1d2-150">Not used</span></span>|  
|<span data-ttu-id="0a1d2-151">7</span><span class="sxs-lookup"><span data-stu-id="0a1d2-151">7</span></span>|<span data-ttu-id="0a1d2-152">未定义</span><span class="sxs-lookup"><span data-stu-id="0a1d2-152">Undefined</span></span>|  
|<span data-ttu-id="0a1d2-153">8</span><span class="sxs-lookup"><span data-stu-id="0a1d2-153">8</span></span>|<span data-ttu-id="0a1d2-154">未使用</span><span class="sxs-lookup"><span data-stu-id="0a1d2-154">Not used</span></span>|  
|<span data-ttu-id="0a1d2-155">9</span><span class="sxs-lookup"><span data-stu-id="0a1d2-155">9</span></span>|`SLong`|  
|<span data-ttu-id="0a1d2-156">10</span><span class="sxs-lookup"><span data-stu-id="0a1d2-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="0a1d2-157">示例</span><span class="sxs-lookup"><span data-stu-id="0a1d2-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0a1d2-158">描述</span><span class="sxs-lookup"><span data-stu-id="0a1d2-158">Description</span></span>  
 <span data-ttu-id="0a1d2-159">下面的代码示例读取并显示文件中的元数据的七个部分`FakePhoto.jpg`。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="0a1d2-160">列表中的第二个 （索引 1） 属性项具有<xref:System.Drawing.Imaging.PropertyItem.Id%2A>0x010F （设备制造商） 和<xref:System.Drawing.Imaging.PropertyItem.Type%2A>2 （ASCII 编码的字节数组）。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="0a1d2-161">此代码示例显示了该属性项的值。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="0a1d2-162">此代码产生类似于下面的输出：</span><span class="sxs-lookup"><span data-stu-id="0a1d2-162">The code produces output similar to the following:</span></span>  
  
 `Property Item 0`  
  
 `id: 0x320`  
  
 `type: 2`  
  
 `length: 16 bytes`  
  
 `Property Item 1`  
  
 `id: 0x10f`  
  
 `type: 2`  
  
 `length: 17 bytes`  
  
 `Property Item 2`  
  
 `id: 0x110`  
  
 `type: 2`  
  
 `length: 7 bytes`  
  
 `Property Item 3`  
  
 `id: 0x9003`  
  
 `type: 2`  
  
 `length: 20 bytes`  
  
 `Property Item 4`  
  
 `id: 0x829a`  
  
 `type: 5`  
  
 `length: 8 bytes`  
  
 `Property Item 5`  
  
 `id: 0x5090`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `Property Item 6`  
  
 `id: 0x5091`  
  
 `type: 3`  
  
 `length: 128 bytes`  
  
 `The equipment make is Northwind Camera.`  
  
### <a name="code"></a><span data-ttu-id="0a1d2-163">代码</span><span class="sxs-lookup"><span data-stu-id="0a1d2-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0a1d2-164">编译代码</span><span class="sxs-lookup"><span data-stu-id="0a1d2-164">Compiling the Code</span></span>  
 <span data-ttu-id="0a1d2-165">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="0a1d2-166">处理窗体的<xref:System.Windows.Forms.Control.Paint>事件并将此代码粘贴到 paint 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="0a1d2-167">必须将`FakePhoto.jpg`用的映像名称和路径对系统和导入有效`System.Drawing.Imaging`命名空间。</span><span class="sxs-lookup"><span data-stu-id="0a1d2-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a1d2-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a1d2-168">See Also</span></span>  
 [<span data-ttu-id="0a1d2-169">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="0a1d2-169">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="0a1d2-170">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="0a1d2-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
