---
title: 如何：为 ToolStrip 控件创建和设置自定义呈现器
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
ms.openlocfilehash: ad5ced42754fba6a714452220dd824c4f54fb5e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743419"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정
<xref:System.Windows.Forms.ToolStrip> 控件可以轻松地支持主题和样式。 可以通过将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性或 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器来实现完全自定义的外观和行为（外观和感觉）。  
  
 可以将呈现器分配给每个 <xref:System.Windows.Forms.ToolStrip>、<xref:System.Windows.Forms.MenuStrip>、<xref:System.Windows.Forms.ContextMenuStrip>或 <xref:System.Windows.Forms.StatusStrip> 控件，也可以通过将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 属性设置为 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 来使用 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>属性来影响所有对象。  
  
> [!NOTE]
> 仅当 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 的值不 `null`时，<xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 才返回 <xref:System.Windows.Forms.ToolStripRenderMode.Custom>。  
  
### <a name="to-create-a-custom-renderer"></a>创建自定义呈现器  
  
1. 扩展 <xref:System.Windows.Forms.ToolStripRenderer> 类。  
  
2. 通过重写适当*的*来实现所需的自定义呈现 멤버  
  
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
  
1. 若要为一个 <xref:System.Windows.Forms.ToolStrip>设置自定义呈现器，请将 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 或者，为应用程序中包含的所有 <xref:System.Windows.Forms.ToolStrip> 类设置自定义呈现器：将 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 属性设置为自定义呈现器并将 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。  
  
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
- [ToolStrip 컨트롤 개요](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 컨트롤 아키텍처](toolstrip-control-architecture.md)
- [ToolStrip 기술 요약](toolstrip-technology-summary.md)
