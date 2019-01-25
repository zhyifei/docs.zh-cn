---
title: 如何：水平拆分窗口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: 651e265b337b106779aeefdfa49decd3725f1a53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701451"
---
# <a name="how-to-split-a-window-horizontally"></a>如何：水平拆分窗口
下面的代码示例进行划分的拆分器<xref:System.Windows.Forms.SplitContainer>控制水平。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.SplitContainer.Orientation%2A>属性的<xref:System.Windows.Forms.SplitContainer>控件将确定拆分器，而不是控件本身的方向。  
  
### <a name="to-split-a-window-horizontally"></a>若要水平拆分窗口  
  
1.  在程序中，设置<xref:System.Windows.Forms.SplitContainer.Orientation%2A>的属性<xref:System.Windows.Forms.SplitContainer>控制对<xref:System.Windows.Forms.Orientation.Horizontal>。  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 控件](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
