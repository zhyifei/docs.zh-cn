---
title: "如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器"
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
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ad328af3aed9a319fe80d829b9556e867533e601
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>如何：在 Windows 窗体中为 ToolStrip 控件创建和设置自定义呈现器
<xref:System.Windows.Forms.ToolStrip>控件向主题和样式轻松支持。 你可以通过设置实现完全自定义外观和行为 （外观和感觉）<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>属性或<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>到自定义呈现器的属性。  
  
 你可以将呈现器分配给每个单独<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.ContextMenuStrip>，或<xref:System.Windows.Forms.StatusStrip>控件，也可以使用<xref:System.Windows.Forms.ToolStripManager.Renderer%2A>属性以影响所有对象通过设置<xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>属性<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>返回<xref:System.Windows.Forms.ToolStripRenderMode.Custom>才的值<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>不`null`。  
  
### <a name="to-create-a-custom-renderer"></a>若要创建自定义呈现器  
  
1.  扩展<xref:System.Windows.Forms.ToolStripRenderer>类。  
  
2.  实现所需的自定义呈现通过重写相应*上...* 成员  
  
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
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>若要设置为当前呈现器的自定义呈现器  
  
1.  若要设置一个自定义呈现器<xref:System.Windows.Forms.ToolStrip>，将其设置<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>到自定义呈现器的属性。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  也可以将设置所有的自定义呈现器<xref:System.Windows.Forms.ToolStrip>你的应用程序中包含的类： 设置<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>到自定义呈现器和集属性<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>属性<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 控件体系结构](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 技术摘要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
