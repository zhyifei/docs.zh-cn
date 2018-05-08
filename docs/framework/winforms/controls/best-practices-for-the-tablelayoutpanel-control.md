---
title: TableLayoutPanel 控件的最佳做法
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>TableLayoutPanel 控件的最佳做法
<xref:System.Windows.Forms.TableLayoutPanel>控件提供了强大的布局功能，应在 Windows 窗体上使用之前应该认真考虑。  
  
## <a name="recommendations"></a>建议  
 以下建议将帮助你使用<xref:System.Windows.Forms.TableLayoutPanel>其充分利用的控件。  
  
### <a name="targeted-use"></a>目标的使用  
 使用<xref:System.Windows.Forms.TableLayoutPanel>尽量少控制。 你不应在要求可调整大小的布局的所有情况下使用它。 以下列表介绍了利用从受益最大的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：  
  
-   其中有相互成比例调整大小的多个部分的窗体的布局。  
  
-   将修改或动态生成在运行时，如具有加上或减去的用户可自定义字段的数据输入窗体根据首选项的布局。  
  
-   应保留在总体的固定大小的布局。 例如，你可能有一个对话框，应保持小于 800 x 600，但你需要支持本地化的字符串。  
  
 以下列表介绍执行不会大大受益于使用的布局<xref:System.Windows.Forms.TableLayoutPanel>控件：  
  
-   简单数据输入窗体与单个列的标签和文本输入区域的单个列。  
  
-   含有单个较大的窗体显示应填满所有可用的空间，在调整大小时的区域。 此示例是窗体中显示单个<xref:System.Windows.Forms.PropertyGrid>控件。 在这种情况下，使用锚定，因为没有任何其他应展开时调整窗体。  
  
 请仔细选择哪些控件需要在<xref:System.Windows.Forms.TableLayoutPanel>控件。 如果你有为你的文本使用锚定的 30%的增长留出空间，请考虑使用<xref:System.Windows.Forms.Control.Anchor%2A>仅属性。 如果你可以估计需要你的布局的空间，使用的<xref:System.Windows.Forms.Control.Dock%2A>和<xref:System.Windows.Forms.Control.Anchor%2A>比估计剩余空间的详细信息和<xref:System.Windows.Forms.Control.AutoSize%2A>行为。  
  
 通常，在设计你使用的布局时<xref:System.Windows.Forms.TableLayoutPanel>控制，使设计保持尽可能简单。  
  
### <a name="use-the-document-outline-window"></a>使用文档大纲窗口  
 文档大纲窗口提供了你的布局，可用于处理你的控件的 z 顺序和父-子关系的树视图。 从**视图菜单**，选择**其他窗口**，然后选择**文档大纲**。  
  
### <a name="avoid-nesting"></a>避免嵌套  
 避免嵌套其他<xref:System.Windows.Forms.TableLayoutPanel>内控制<xref:System.Windows.Forms.TableLayoutPanel>控件。 调试嵌套的布局可能很困难。  
  
### <a name="avoid-visual-inheritance"></a>避免 Visual 继承  
 <xref:System.Windows.Forms.TableLayoutPanel>控件不支持在 Windows 窗体设计器 visual 继承。 A<xref:System.Windows.Forms.TableLayoutPanel>为"已锁定"在设计时，将出现在派生类中的控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
