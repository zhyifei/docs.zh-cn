---
title: 使用双缓冲
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 9b09210eba0ac3a141219a7cdbff15f22c6ed003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523905"
---
# <a name="using-double-buffering"></a>使用双缓冲
可以使用双缓冲图形来减少闪烁包含复杂的绘制操作的应用程序中。 .NET Framework 包含双缓冲的内置支持，或者你可以管理并手动呈现图形。  
  
## <a name="in-this-section"></a>本节内容  
 [双缓冲的图形](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 引入了双缓冲的概念和概述了.NET Framework 支持。  
  
 [如何：通过对窗体和控件使用双缓冲来减少图形闪烁](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 演示如何使用双缓冲支持.NET Framework 中的默认值。  
  
 [如何：手动管理缓冲的图形](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 演示如何管理应用程序中的双缓冲。  
  
 [如何：手动呈现缓冲的图形](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 演示如何呈现双缓冲图形。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 启用双缓冲的控制方法。  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 提供用于创建图形缓冲区的方法。  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 您可以访问应用程序域的缓冲的图形上下文。
