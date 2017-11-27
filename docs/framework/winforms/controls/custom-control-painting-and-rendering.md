---
title: "自定义控件的绘制和呈现"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: babf3d235f4cca61ad6d0e5fdc4e6b6146c7d060
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="custom-control-painting-and-rendering"></a>自定义控件的绘制和呈现
自定义绘制的控件是由.NET Framework 轻松的许多复杂任务之一。 在创作时自定义控件，你会有很多选项有关控件的图形的外观。 如果创作继承自的控件`Control`，必须提供代码，使控件呈现其图形表示形式。 如果你通过继承创建用户控件`UserControl`，或继承从一个 Windows 窗体控件，你可能重写的标准的图形表示形式并提供你自己的图形代码。 如果你想要提供自定义呈现的构成控件`UserControl`创作，你的选项变得更为有限，但仍允许各种控件和应用程序的图形化可能性。  
  
## <a name="in-this-section"></a>本节内容  
 [呈现 Windows 窗体控件](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 演示如何程序显示一个控件的逻辑。  
  
 [用户绘制的控件](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 提供编写和重写为您的控件的呈现代码中所涉及的步骤的概述。  
  
 [构成控件](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 描述如何在你的用户控件和窗体中实现构成控件的自定义呈现代码。  
  
 [如何：将控件设为在运行时不可见](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 演示如何使用<xref:System.Windows.Forms.Control.Visible%2A>属性来隐藏和显示一个控件。  
  
 [如何：为控件设置透明背景](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 演示如何使用<xref:System.Windows.Forms.Control.SetStyle%2A>方法来创建不透明、 透明的或部分透明背景色。  
  
 [使用视觉样式呈现控件](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 演示如何呈现控件支持它们的操作系统中使用视觉样式。  
  
## <a name="reference"></a>参考  
 <xref:System.Windows.Forms.Control>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.UserControl>  
 对此类进行描述，并提供指向其所有成员的链接。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 介绍了此方法。  
  
## <a name="related-sections"></a>相关章节  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 引入了[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]从 Visual Studio 透视，并提供链接的详细信息的图形功能。  
  
 [各种自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 描述可以创作的自定义控件的类型。
