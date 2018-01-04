---
title: "使用图形容器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244f8e8a280369798daf12f8a61519826f937a4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-graphics-containers"></a>使用图形容器
A<xref:System.Drawing.Graphics>对象提供的方法，如<xref:System.Drawing.Graphics.DrawLine%2A>， <xref:System.Drawing.Graphics.DrawImage%2A>，和<xref:System.Drawing.Graphics.DrawString%2A>用于显示矢量图像、 光栅图像和文本。 A<xref:System.Drawing.Graphics>对象还具有影响的质量和方向绘制的项的多个属性。 例如，平滑模式属性确定是否抗锯齿效果应用于直线和曲线，和世界变换属性影响的位置和旋转绘制的项。  
  
 A<xref:System.Drawing.Graphics>对象是与特定显示设备相关联。 当你使用<xref:System.Drawing.Graphics>对象以在窗口中，绘制<xref:System.Drawing.Graphics>对象也是与该特定窗口相关联。  
  
 A<xref:System.Drawing.Graphics>对象可以被认为是作为容器因为它包含一组影响绘制的属性并将它链接到特定于设备的信息。 你可以创建中的现有的辅助容器<xref:System.Drawing.Graphics>对象通过调用<xref:System.Drawing.Graphics.BeginContainer%2A>方法，<xref:System.Drawing.Graphics>对象。  
  
## <a name="in-this-section"></a>本节内容  
 [管理图形对象的状态](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 描述如何管理质量设置、 剪辑区域和转换的<xref:System.Drawing.Graphics>对象。  
  
 [使用嵌套的图形容器](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 演示如何使用容器来控制的状态<xref:System.Drawing.Graphics>对象。
