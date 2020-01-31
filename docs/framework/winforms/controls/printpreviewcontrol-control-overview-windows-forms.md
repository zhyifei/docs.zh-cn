---
title: PrintPreviewControl 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741439"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a>PrintPreviewControl 컨트롤 개요(Windows Forms)
Windows 窗体 <xref:System.Windows.Forms.PrintPreviewControl> 用于显示[PrintDocument](printdocument-component-windows-forms.md) ，因为它会在打印时显示。 이 컨트롤에는 단추나 다른 사용자 인터페이스 요소가 없으므로, 일반적으로 고유한 인쇄 미리 보기 사용자 인터페이스를 작성하려는 경우에만 <xref:System.Windows.Forms.PrintPreviewControl>을 사용합니다. 如果需要标准用户界面，请使用 <xref:System.Windows.Forms.PrintPreviewDialog> 控件;有关概述，请参阅[PrintPreviewDialog 控件概述](printpreviewdialog-control-overview-windows-forms.md)。  
  
## <a name="key-properties"></a>키 속성  
 控件的键属性为 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>，这将设置要预览的文档。 文档必须是 <xref:System.Drawing.Printing.PrintDocument> 的对象。 有关创建打印文档的概述，请参阅[PrintDocument 组件概述](printdocument-component-overview-windows-forms.md)和[Windows 窗体打印支持](../advanced/windows-forms-print-support.md)。 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 和 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 属性确定控件上水平和垂直显示的页数。 抗锯齿可以使文本显示得更平滑，但也可以使显示速度变慢;若要使用它，请将 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 属性设置为 `true`。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.PrintPreviewControl>
- [PrintPreviewDialog 컨트롤 개요](printpreviewdialog-control-overview-windows-forms.md)
- [PrintPreviewControl 컨트롤](printpreviewcontrol-control-windows-forms.md)
- [대화 상자 컨트롤 및 구성 요소](dialog-box-controls-and-components-windows-forms.md)
