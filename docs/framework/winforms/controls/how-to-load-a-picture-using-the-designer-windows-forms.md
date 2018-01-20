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
ms.workload: dotnet
ms.openlocfilehash: 1dec3c71c0c93ce580925744fe55f05cd2e5f383
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>如何：使用设计器加载图片（Windows 窗体）
在 Windows 窗体<xref:System.Windows.Forms.PictureBox>控件，可以加载并将图片窗体上显示在设计时，通过设置<xref:System.Windows.Forms.PictureBox.Image%2A>属性设置为有效的图片。 下表显示可接受文件类型。  
  
|类型|文件扩展名|  
|----------|-------------------------|  
|Bitmap|.bmp|  
|图标|.ico|  
|GIF|.gif|  
|图元文件|.wmf|  
|JPEG|.jpg|  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-display-a-picture-at-design-time"></a>要在设计时显示的图片  
  
1.  绘制<xref:System.Windows.Forms.PictureBox>窗体上的控件。  
  
2.  在属性窗口中，选择<xref:System.Windows.Forms.PictureBox.Image%2A>属性，然后单击省略号按钮以显示**打开**对话框。  
  
3.  如果你要查找特定文件类型 （例如，.gif 文件），选择在**类型的文件**框。  
  
4.  选择你想要显示的文件。  
  
### <a name="to-clear-the-picture-at-design-time"></a>若要在设计时清除图片  
  
1.  上**属性**窗口中，选择<xref:System.Windows.Forms.PictureBox.Image%2A>属性并右键单击显示的图像对象的名称左侧的小缩略图。 选择**重置**。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.PictureBox>  
 [PictureBox 控件概述](../../../../docs/framework/winforms/controls/picturebox-control-overview-windows-forms.md)  
 [如何：在运行时修改图片的大小或位置](../../../../docs/framework/winforms/controls/how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)  
 [如何：在运行时设置图片](../../../../docs/framework/winforms/controls/how-to-set-pictures-at-run-time-windows-forms.md)  
 [PictureBox 控件](../../../../docs/framework/winforms/controls/picturebox-control-windows-forms.md)
