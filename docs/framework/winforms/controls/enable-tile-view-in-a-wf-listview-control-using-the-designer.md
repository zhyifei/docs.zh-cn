---
title: "如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72fc1212e6e154cf3459d9ae6b94b6a8965fb151
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图
磁贴视图功能<xref:System.Windows.Forms.ListView>控制，你可以提供一种视觉平衡图形和文本信息之间。 磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。 磁贴视图功能结合的分组或插入标记中的功能<xref:System.Windows.Forms.ListView>控件。  
  
 磁贴视图使用 32 x 32 图标和若干行文本，如在下图中所示。  
  
 ![平铺 ListView 控件中的视图](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 平铺视图属性和方法，可以指定哪些列字段以显示每个项，以及共同控制的大小和磁贴视图窗口中的所有项的外观。 为清楚起见，将磁贴中的第一行始终是文本的项的名称;它不能更改。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.ListView>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。  
  
> [!NOTE]
>  当应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法时，磁贴视图仅适用于 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]。 在早期的操作系统上，任何与磁贴视图相关的代码都不起作用，且 <xref:System.Windows.Forms.ListView> 控件将显示在大图标视图中。 有关详细信息，请参阅<xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>。  
>   
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-set-tile-view-in-the-designer"></a>若要设置设计器中的磁贴视图  
  
1.  选择<xref:System.Windows.Forms.ListView>窗体上的控件。  
  
2.  在**属性**窗口中，选择<xref:System.Windows.Forms.ListView.View%2A>属性，然后选择**磁贴**。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListView.TileSize%2A>  
 [Windows XP 功能和 Windows 窗体控件](http://msdn.microsoft.com/library/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
