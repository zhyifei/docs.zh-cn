---
title: "双缓冲图形"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double buffering
- graphics [Windows Forms], double-buffered
- flicker [Windows Forms], reducing with double buffering
- examples [Windows Forms], double-buffered graphics
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7e4445b0a729eb1f826d17340db02f0c56149b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="double-buffered-graphics"></a>双缓冲图形
对图形进行编程时出现闪烁是一个常见问题。 需要多个复杂画图操作的图形操作可导致呈现的图像出现闪烁或具有不可接受的外观。 为解决这些问题，.NET Framework 提供了双缓冲功能。  
  
 双缓冲使用内容缓冲来解决与多个画图操作相关的闪烁问题。 启用双缓冲后，所有画图操作会首先呈现到内存缓冲而不是屏幕上的绘图图面。 所有画图操作完成后，内存缓冲会直接复制到与之关联的绘图图面。 由于屏幕上仅执行一个图形操作，因此与复杂画图操作相关的图像闪烁可得以消除。  
  
## <a name="default-double-buffering"></a>默认双缓冲  
 在应用程序中使用双缓冲的最简单方式是对 .NET Framework 所提供的的窗体和控件使用默认双缓冲。 你可以启用默认双缓冲为 Windows 窗体并通过设置创作 Windows 控件<xref:System.Windows.Forms.Control.DoubleBuffered%2A>属性`true`或通过使用<xref:System.Windows.Forms.Control.SetStyle%2A>方法。 有关详细信息，请参阅[如何：通过对窗体和控件使用双缓冲来减少图形闪烁](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)。  
  
## <a name="manually-managing-buffered-graphics"></a>手动管理缓冲图形  
 对于更高级的双缓冲方案（如动画或高级内存管理），可使用 .NET Framework 类来实现自己的双缓冲逻辑。 类负责分配和管理各自的图形缓冲区是<xref:System.Drawing.BufferedGraphicsContext>类。 每个应用程序域都有自己的默认<xref:System.Drawing.BufferedGraphicsContext>管理所有默认双缓冲为该应用程序的实例。 在大多数情况下将有一个应用程序域，每个应用程序，因此通常一个默认<xref:System.Drawing.BufferedGraphicsContext>每个应用程序。 默认<xref:System.Drawing.BufferedGraphicsContext>实例由<xref:System.Drawing.BufferedGraphicsManager>类。 你可以检索默认值对的引用<xref:System.Drawing.BufferedGraphicsContext>实例通过调用<xref:System.Drawing.BufferedGraphicsManager.Current%2A>。 你还可以创建专用<xref:System.Drawing.BufferedGraphicsContext>实例，这可以提高图形密集型应用程序的性能。 有关如何创建<xref:System.Drawing.BufferedGraphicsContext>实例，请参阅[如何： 手动管理缓冲图形](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)。  
  
## <a name="manually-displaying-buffered-graphics"></a>手动显示缓冲图形  
 你可以使用的实例<xref:System.Drawing.BufferedGraphicsContext>类通过调用创建图形缓冲区<xref:System.Drawing.BufferedGraphicsContext.Allocate%2A?displayProperty=nameWithType>，它返回的实例<xref:System.Drawing.BufferedGraphics>类。 A<xref:System.Drawing.BufferedGraphics>对象管理与呈现图面，如窗体或控件相关联的内存缓冲区。  
  
 实例化后，<xref:System.Drawing.BufferedGraphics>类管理到内存中图形缓冲区的呈现。 你可以呈现到内存缓冲区中通过图形<xref:System.Drawing.BufferedGraphics.Graphics%2A>，这会公开<xref:System.Drawing.Graphics>直接表示内存缓冲区的对象。 你可以绘制到此<xref:System.Drawing.Graphics>对象就像到<xref:System.Drawing.Graphics>对象，它表示绘图图面。 所有图形都绘制到的缓冲区之后，你可以使用<xref:System.Drawing.BufferedGraphics.Render%2A?displayProperty=nameWithType>将缓冲区的内容复制到在屏幕上的绘图图面。  
  
 有关详细信息使用<xref:System.Drawing.BufferedGraphics>类，请参阅[手动呈现缓冲图形](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)。 有关呈现图形的详细信息，请参阅 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Drawing.BufferedGraphics>  
 <xref:System.Drawing.BufferedGraphicsContext>  
 <xref:System.Drawing.BufferedGraphicsManager>  
 [如何：手动呈现缓冲的图形](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 [如何：通过对窗体和控件使用双缓冲来减少图形闪烁](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 [如何：手动管理缓冲的图形](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
