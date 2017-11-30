---
title: "如何：定义拆分窗口中的大小调整和定位行为"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: db4a99c7dae7783e8ea51f43ad51fcd2214997e5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>如何：定义拆分窗口中的大小调整和定位行为
面板的<xref:System.Windows.Forms.SplitContainer>控制有助于使自身对其大小调整和由用户操作。 但是，将有的时候你将想要以编程方式控制拆分器-它位于，其中可以移动的程度。  
  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性和其他属性上的<xref:System.Windows.Forms.SplitContainer>控件使你的用户界面以满足你需求的行为的精确控制。 下表中列出了这些属性。  
  
|名称|描述|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 属性|确定是否通过键盘或鼠标可移动拆分器。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 属性|确定以到可移动拆分条从左侧或右上边缘像素为单位的距离。|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 属性|确定的最小距离，以像素为单位，用户可以移动拆分器。|  
  
 下面的示例修改<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性来创建"对齐拆分"的效果; 当用户拖动拆分器，递增的 10 个像素，而不是默认值 1 单位。  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>若要定义 SplitContainer，调整大小行为  
  
1.  在过程中，设置<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>属性设置为所需的大小，以便实现拆分器的对齐行为。  
  
     在以下代码示例中，在窗体的<xref:System.Windows.Forms.Form.Load>事件、 中的拆分<xref:System.Windows.Forms.SplitContainer>控件设置跳转时拖放的 10 个像素。  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) 将以下代码放在窗体的构造函数以注册事件处理程序。  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     略有向左或向右移动拆分器会有明显的效果;但是，当鼠标指针的两个方向的 10 个像素，拆分器将与新的位置对齐。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
