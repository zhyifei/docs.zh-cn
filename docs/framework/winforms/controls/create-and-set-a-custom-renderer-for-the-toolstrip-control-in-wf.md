---
title: 如何：为工具条控件创建和设置自定义渲染器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182407"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器
<xref:System.Windows.Forms.ToolStrip>控件为主题和样式提供了简单的支持。 通过将属性或属性设置为自定义呈现器，<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType><xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>可以完全自定义外观和行为（外观）。  
  
 <xref:System.Windows.Forms.ToolStrip>可以将渲染器分配给每个单独的 、、<xref:System.Windows.Forms.ContextMenuStrip><xref:System.Windows.Forms.StatusStrip><xref:System.Windows.Forms.ToolStripManager.Renderer%2A><xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType><xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType><xref:System.Windows.Forms.MenuStrip>或控件，也可以使用 属性通过将 属性设置为 来影响所有对象。  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>仅当<xref:System.Windows.Forms.ToolStripRenderMode.Custom>的值<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>不是`null`时才返回。  
  
### <a name="to-create-a-custom-renderer"></a>创建自定义渲染器  
  
1. 扩展类<xref:System.Windows.Forms.ToolStripRenderer>。  
  
2. 通过重写适当的*On...* members  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>将自定义渲染器设置为当前渲染器  
  
1. 要为其中<xref:System.Windows.Forms.ToolStrip>设置自定义呈现器，将<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>属性设置为自定义呈现器。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 或者为应用程序中包含的<xref:System.Windows.Forms.ToolStrip>所有类设置自定义呈现器：将<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>属性设置为自定义呈现器，<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>并将该属性设置为<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
