---
title: 使用设计器在 ListView 控件中启用磁贴视图
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: a0429efaab14995ab1e3f3b0dfd91db61de72fbf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745800"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a>如何：使用设计器在 Windows 窗体 ListView 控件中启用平铺视图
利用 <xref:System.Windows.Forms.ListView> 控件的磁贴视图功能，可以在图形和文本信息之间提供视觉平衡。 磁贴视图中，为项目显示的文本信息与为详细信息视图定义的列信息相同。 平铺视图函数与 <xref:System.Windows.Forms.ListView> 控件中的分组或插入标记功能结合在一起。

 磁贴视图使用 32 x 32 图标和几行文本，如下图所示。

 ![ListView 控件中的平铺视图](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "磁贴视图图标和文本")

 利用磁贴视图属性和方法，您可以指定要为每个项显示的列字段，以及共同控制平铺视图窗口中所有项的大小和外观。 为清楚起见，磁贴中的第一行文本始终是项的名称;不能更改它。

 下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.ListView> 控件的窗体。 有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。

## <a name="to-set-tile-view-in-the-designer"></a>在设计器中设置磁贴视图

1. 在 Visual Studio 中，选择窗体上的 "<xref:System.Windows.Forms.ListView>" 控件。

2. 在 "**属性**" 窗口中，选择 "<xref:System.Windows.Forms.ListView.View%2A>" 属性，然后选择 "**磁贴**"。

## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView 控件概述](listview-control-overview-windows-forms.md)
