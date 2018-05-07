---
title: Windows 窗体坐标
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: ba6bf8c1a8ae5ab14a9b33ae431e34310046b2a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="windows-forms-coordinates"></a>Windows 窗体坐标
Windows 窗体坐标系统基于设备坐标，并度量值时在 Windows 窗体中绘制的基本单位是设备单元 （通常情况下，像素）。 在屏幕上的点的 x 坐标和 y 坐标对所述增加到右侧和 y 坐标增加从顶部到底部的 x 坐标。 来源，相对于屏幕中，位置将有所不同具体取决于是否指定屏幕或客户端坐标。  
  
## <a name="screen-coordinates"></a>屏幕坐标  
 Windows 窗体应用程序指定屏幕坐标中的屏幕上窗口的位置。 屏幕坐标的来源是屏幕的左上角。 窗口的完整位置通常由<xref:System.Drawing.Rectangle>结构，它包含两个定义窗口的左上角和右下角的点的屏幕坐标。  
  
## <a name="client-coordinates"></a>客户端坐标  
 Windows 窗体应用程序窗体或控件使用客户端坐标中指定的点的位置。 工作区坐标中的源是控件或窗体的工作区的左上角。 客户端坐标可确保在应用程序可以在窗体或控件，无论窗体或屏幕上的控件的位置中绘制时使用一致的坐标值。  
  
 客户端区域的尺寸，还介绍了由<xref:System.Drawing.Rectangle>结构，其中包含工作区坐标中的区。 在所有情况下，矩形的左上角的坐标包含在客户端区域中，，而不对此右下角坐标。 图形操作不包括的客户端区域的上边缘右和下边缘。 例如<xref:System.Drawing.Graphics.FillRectangle%2A>方法将一直填充到指定的矩形的上边缘右和下边缘，但不是会包括这些边缘。  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>将映射到另一种类型的坐标从  
 有时，你可能需要从屏幕坐标映射到客户端坐标。 你可以轻松地实现此目的使用<xref:System.Windows.Forms.Control.PointToClient%2A>和<xref:System.Windows.Forms.Control.PointToScreen%2A>方法中提供<xref:System.Windows.Forms.Control>类。 例如，<xref:System.Windows.Forms.Control.MousePosition%2A>属性<xref:System.Windows.Forms.Control>报告在屏幕坐标中，但你可能想要将它们转换成工作区坐标。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Control.PointToClient%2A>  
 <xref:System.Windows.Forms.Control.PointToScreen%2A>
