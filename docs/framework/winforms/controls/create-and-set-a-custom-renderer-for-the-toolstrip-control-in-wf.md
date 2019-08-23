---
title: 如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器
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
ms.openlocfilehash: c354ace3a7d3ce43f549dd1295a85fbee004eb22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929729"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器
<xref:System.Windows.Forms.ToolStrip>控件提供对主题和样式的简单支持。 可以通过将<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>属性<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>或属性设置为自定义呈现器来实现完全自定义的外观和行为 (外观和风格)。  
  
 可以<xref:System.Windows.Forms.ToolStrip>向每个单独<xref:System.Windows.Forms.ContextMenuStrip>的<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>、 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.StatusStrip> 或控件<xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>分配呈现器, 也可以通过将属性设置为来使用属性来影响所有对象。<xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
  
> [!NOTE]
> <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>仅<xref:System.Windows.Forms.ToolStripRenderMode.Custom>当的<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>值不`null`为时返回。  
  
### <a name="to-create-a-custom-renderer"></a>创建自定义呈现器  
  
1. <xref:System.Windows.Forms.ToolStripRenderer>扩展类。  
  
2. 通过重写适当*的*来实现所需的自定义呈现 成员  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>将自定义呈现器设置为当前呈现器  
  
1. 若要设置一个<xref:System.Windows.Forms.ToolStrip>自定义呈现器, 请<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>将属性设置为自定义呈现器。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 或为应用程序中包含的所有<xref:System.Windows.Forms.ToolStrip>类设置自定义呈现器:将属性设置为自定义呈现器并<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>将属性设置<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>为。 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
