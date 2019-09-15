---
title: 如何：读取图像元数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 8294bc6596c408160a50d9d7d5e6154f66025c73
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988568"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="ab686-102">如何：读取图像元数据</span><span class="sxs-lookup"><span data-stu-id="ab686-102">How to: Read Image Metadata</span></span>
<span data-ttu-id="ab686-103">某些图像文件包含元数据，您可以读取这些元数据来确定图像的功能。</span><span class="sxs-lookup"><span data-stu-id="ab686-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="ab686-104">例如，数字照片可能包含元数据，您可以读取这些元数据来确定用于捕获图像的相机的品牌和型号。</span><span class="sxs-lookup"><span data-stu-id="ab686-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="ab686-105">利用 GDI +，可以读取现有的元数据，还可以将新的元数据写入到图像文件。</span><span class="sxs-lookup"><span data-stu-id="ab686-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>  
  
 <span data-ttu-id="ab686-106">Gdi + 将<xref:System.Drawing.Imaging.PropertyItem>单独的元数据存储在对象中。</span><span class="sxs-lookup"><span data-stu-id="ab686-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="ab686-107">您可以读取<xref:System.Drawing.Image>对象<xref:System.Drawing.Image.PropertyItems%2A>的属性，以从文件中检索所有元数据。</span><span class="sxs-lookup"><span data-stu-id="ab686-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="ab686-108">属性返回对象的<xref:System.Drawing.Imaging.PropertyItem>数组。 <xref:System.Drawing.Image.PropertyItems%2A></span><span class="sxs-lookup"><span data-stu-id="ab686-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>  
  
 <span data-ttu-id="ab686-109">`Value` `Id` `Type` `Len`对象具有以下四个属性：、、和。 <xref:System.Drawing.Imaging.PropertyItem></span><span class="sxs-lookup"><span data-stu-id="ab686-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>  
  
## <a name="id"></a><span data-ttu-id="ab686-110">Id</span><span class="sxs-lookup"><span data-stu-id="ab686-110">Id</span></span>  
 <span data-ttu-id="ab686-111">标识元数据项的标记。</span><span class="sxs-lookup"><span data-stu-id="ab686-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="ab686-112">下表显示了可以分配给<xref:System.Drawing.Imaging.PropertyItem.Id%2A>的一些值。</span><span class="sxs-lookup"><span data-stu-id="ab686-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table.</span></span>  
  
|<span data-ttu-id="ab686-113">十六进制值</span><span class="sxs-lookup"><span data-stu-id="ab686-113">Hexadecimal value</span></span>|<span data-ttu-id="ab686-114">描述</span><span class="sxs-lookup"><span data-stu-id="ab686-114">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="ab686-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="ab686-115">0x0320</span></span><br /><br /> <span data-ttu-id="ab686-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="ab686-116">0x010F</span></span><br /><br /> <span data-ttu-id="ab686-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="ab686-117">0x0110</span></span><br /><br /> <span data-ttu-id="ab686-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="ab686-118">0x9003</span></span><br /><br /> <span data-ttu-id="ab686-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="ab686-119">0x829A</span></span><br /><br /> <span data-ttu-id="ab686-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="ab686-120">0x5090</span></span><br /><br /> <span data-ttu-id="ab686-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="ab686-121">0x5091</span></span>|<span data-ttu-id="ab686-122">图像标题</span><span class="sxs-lookup"><span data-stu-id="ab686-122">Image title</span></span><br /><br /> <span data-ttu-id="ab686-123">设备制造商</span><span class="sxs-lookup"><span data-stu-id="ab686-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="ab686-124">设备型号</span><span class="sxs-lookup"><span data-stu-id="ab686-124">Equipment model</span></span><br /><br /> <span data-ttu-id="ab686-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="ab686-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="ab686-126">Exif 曝光时间</span><span class="sxs-lookup"><span data-stu-id="ab686-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="ab686-127">亮度表</span><span class="sxs-lookup"><span data-stu-id="ab686-127">Luminance table</span></span><br /><br /> <span data-ttu-id="ab686-128">色度表</span><span class="sxs-lookup"><span data-stu-id="ab686-128">Chrominance table</span></span>|  
  
## <a name="value"></a><span data-ttu-id="ab686-129">值</span><span class="sxs-lookup"><span data-stu-id="ab686-129">Value</span></span>  
 <span data-ttu-id="ab686-130">值的数组。</span><span class="sxs-lookup"><span data-stu-id="ab686-130">An array of values.</span></span> <span data-ttu-id="ab686-131">值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性确定。</span><span class="sxs-lookup"><span data-stu-id="ab686-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>  
  
## <a name="len"></a><span data-ttu-id="ab686-132">Len</span><span class="sxs-lookup"><span data-stu-id="ab686-132">Len</span></span>  
 <span data-ttu-id="ab686-133"><xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性所指向的值数组的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab686-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>  
  
## <a name="type"></a><span data-ttu-id="ab686-134">类型</span><span class="sxs-lookup"><span data-stu-id="ab686-134">Type</span></span>  
 <span data-ttu-id="ab686-135">`Value`属性所指向的数组中的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ab686-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="ab686-136">下表显示了`Type`属性值指示的格式</span><span class="sxs-lookup"><span data-stu-id="ab686-136">The formats indicated by the `Type` property values are shown in the following table</span></span>  
  
|<span data-ttu-id="ab686-137">数值</span><span class="sxs-lookup"><span data-stu-id="ab686-137">Numeric value</span></span>|<span data-ttu-id="ab686-138">描述</span><span class="sxs-lookup"><span data-stu-id="ab686-138">Description</span></span>|  
|-------------------|-----------------|  
|<span data-ttu-id="ab686-139">1</span><span class="sxs-lookup"><span data-stu-id="ab686-139">1</span></span>|<span data-ttu-id="ab686-140">一个 `Byte`</span><span class="sxs-lookup"><span data-stu-id="ab686-140">A `Byte`</span></span>|  
|<span data-ttu-id="ab686-141">2</span><span class="sxs-lookup"><span data-stu-id="ab686-141">2</span></span>|<span data-ttu-id="ab686-142">编码为 ASCII `Byte`的对象数组</span><span class="sxs-lookup"><span data-stu-id="ab686-142">An array of `Byte` objects encoded as ASCII</span></span>|  
|<span data-ttu-id="ab686-143">3</span><span class="sxs-lookup"><span data-stu-id="ab686-143">3</span></span>|<span data-ttu-id="ab686-144">16位整数</span><span class="sxs-lookup"><span data-stu-id="ab686-144">A 16-bit integer</span></span>|  
|<span data-ttu-id="ab686-145">4</span><span class="sxs-lookup"><span data-stu-id="ab686-145">4</span></span>|<span data-ttu-id="ab686-146">32位整数</span><span class="sxs-lookup"><span data-stu-id="ab686-146">A 32-bit integer</span></span>|  
|<span data-ttu-id="ab686-147">5</span><span class="sxs-lookup"><span data-stu-id="ab686-147">5</span></span>|<span data-ttu-id="ab686-148">表示有理数的两`Byte`个对象组成的数组</span><span class="sxs-lookup"><span data-stu-id="ab686-148">An array of two `Byte` objects that represent a rational number</span></span>|  
|<span data-ttu-id="ab686-149">6</span><span class="sxs-lookup"><span data-stu-id="ab686-149">6</span></span>|<span data-ttu-id="ab686-150">未使用</span><span class="sxs-lookup"><span data-stu-id="ab686-150">Not used</span></span>|  
|<span data-ttu-id="ab686-151">7</span><span class="sxs-lookup"><span data-stu-id="ab686-151">7</span></span>|<span data-ttu-id="ab686-152">未定义</span><span class="sxs-lookup"><span data-stu-id="ab686-152">Undefined</span></span>|  
|<span data-ttu-id="ab686-153">8</span><span class="sxs-lookup"><span data-stu-id="ab686-153">8</span></span>|<span data-ttu-id="ab686-154">未使用</span><span class="sxs-lookup"><span data-stu-id="ab686-154">Not used</span></span>|  
|<span data-ttu-id="ab686-155">9</span><span class="sxs-lookup"><span data-stu-id="ab686-155">9</span></span>|`SLong`|  
|<span data-ttu-id="ab686-156">10</span><span class="sxs-lookup"><span data-stu-id="ab686-156">10</span></span>|`SRational`|  
  
## <a name="example"></a><span data-ttu-id="ab686-157">示例</span><span class="sxs-lookup"><span data-stu-id="ab686-157">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ab686-158">描述</span><span class="sxs-lookup"><span data-stu-id="ab686-158">Description</span></span>  
 <span data-ttu-id="ab686-159">下面的代码示例读取并显示文件`FakePhoto.jpg`中的七个元数据部分。</span><span class="sxs-lookup"><span data-stu-id="ab686-159">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="ab686-160">列表中的第二个（索引1）属性项<xref:System.Drawing.Imaging.PropertyItem.Id%2A>具有0x010F （设备制造商） <xref:System.Drawing.Imaging.PropertyItem.Type%2A>和2（ASCII 编码字节数组）。</span><span class="sxs-lookup"><span data-stu-id="ab686-160">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="ab686-161">此代码示例显示该属性项的值。</span><span class="sxs-lookup"><span data-stu-id="ab686-161">The code example displays the value of that property item.</span></span>  
  
 <span data-ttu-id="ab686-162">此代码生成类似于以下内容的输出：</span><span class="sxs-lookup"><span data-stu-id="ab686-162">The code produces output similar to the following:</span></span>  
 
```output
 Property Item 0
  
 id: 0x320
  
 type: 2
 
 length: 16 bytes 
  
 Property Item 1
  
 id: 0x10f
  
 type: 2 
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```
  
### <a name="code"></a><span data-ttu-id="ab686-163">代码</span><span class="sxs-lookup"><span data-stu-id="ab686-163">Code</span></span>  
 [!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ab686-164">编译代码</span><span class="sxs-lookup"><span data-stu-id="ab686-164">Compiling the Code</span></span>  
 <span data-ttu-id="ab686-165">前面的示例旨在与 Windows 窗体一起使用，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`作为<xref:System.Windows.Forms.Control.Paint>事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="ab686-165">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="ab686-166">处理窗体的<xref:System.Windows.Forms.Control.Paint>事件，并将此代码粘贴到画图事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="ab686-166">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="ab686-167">必须将替换`FakePhoto.jpg`为在系统中有效的映像名称和路径，然后导`System.Drawing.Imaging`入该命名空间。</span><span class="sxs-lookup"><span data-stu-id="ab686-167">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab686-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab686-168">See also</span></span>

- [<span data-ttu-id="ab686-169">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="ab686-169">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="ab686-170">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="ab686-170">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
