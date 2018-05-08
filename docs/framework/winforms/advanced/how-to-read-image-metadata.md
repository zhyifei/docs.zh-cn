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
ms.openlocfilehash: 92ce4eb8d51fbd25f9a129a629dc47bfb9941f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-read-image-metadata"></a>如何：读取图像元数据
某些图像文件包含您可以读取以确定图像的功能的元数据。 例如，数码相片可能包含您可以读取以确定的品牌和型号的照相机用于捕获映像的元数据。 与[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，您可以读取现有的元数据，并且你还可以向图像文件写入新的元数据。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 将存储的元数据的单独片<xref:System.Drawing.Imaging.PropertyItem>对象。 你可以阅读<xref:System.Drawing.Image.PropertyItems%2A>属性<xref:System.Drawing.Image>要从文件中检索所有元数据对象。 <xref:System.Drawing.Image.PropertyItems%2A>属性返回的数组<xref:System.Drawing.Imaging.PropertyItem>对象。  
  
 A<xref:System.Drawing.Imaging.PropertyItem>对象具有以下四个属性： `Id`， `Value`， `Len`，和`Type`。  
  
## <a name="id"></a>Id  
 一个标识元数据项的标记。 可以分配给某些值<xref:System.Drawing.Imaging.PropertyItem.Id%2A>以下表所示。  
  
|十六进制值|描述|  
|-----------------------|-----------------|  
|0x0320<br /><br /> 0x010F<br /><br /> 0x0110<br /><br /> 0x9003<br /><br /> 0x829A<br /><br /> 0x5090<br /><br /> 0x5091|映像标题<br /><br /> 设备制造商<br /><br /> 设备型号<br /><br /> ExifDTOriginal<br /><br /> Exif 暴露时间<br /><br /> 亮度表<br /><br /> 色度表|  
  
## <a name="value"></a>值  
 值的数组。 值的格式由<xref:System.Drawing.Imaging.PropertyItem.Type%2A>属性。  
  
## <a name="len"></a>Len  
 指向的值的数组的长度 （以字节为单位）<xref:System.Drawing.Imaging.PropertyItem.Value%2A>属性。  
  
## <a name="type"></a>类型  
 指向数组中的值的数据类型`Value`属性。 格式由`Type`下表列出了属性值  
  
|数字值|描述|  
|-------------------|-----------------|  
|1|一个 `Byte`|  
|2|数组`Byte`为 ASCII 编码的对象|  
|3|16 位整数|  
|4|一个 32 位整数|  
|5|两个数组`Byte`对象，后者表示有理数|  
|6|未使用|  
|7|未定义|  
|8|未使用|  
|9|`SLong`|  
|10|`SRational`|  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 下面的代码示例读取并显示文件中的元数据的七个部分`FakePhoto.jpg`。 列表中的第二个 （索引 1） 属性项具有<xref:System.Drawing.Imaging.PropertyItem.Id%2A>0x010F （设备制造商） 和<xref:System.Drawing.Imaging.PropertyItem.Type%2A>2 （ASCII 编码的字节数组）。 此代码示例显示了该属性项的值。  
  
 此代码产生类似于下面的输出：  
  
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
  
### <a name="code"></a>代码  
 [!code-csharp[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.WorkingWithImages#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 处理窗体的<xref:System.Windows.Forms.Control.Paint>事件并将此代码粘贴到 paint 事件处理程序。 必须将`FakePhoto.jpg`用的映像名称和路径对系统和导入有效`System.Drawing.Imaging`命名空间。  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
