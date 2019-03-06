---
title: 如何：清除自定义控件上的墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365888"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="4422b-102">如何：清除自定义控件上的墨迹</span><span class="sxs-lookup"><span data-stu-id="4422b-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="4422b-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester>确定当前绘制的笔画是否与另一个笔画相交。</span><span class="sxs-lookup"><span data-stu-id="4422b-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="4422b-104">对于创建控件，使用户擦除笔划的部分，这很有用，方式用户可以在<xref:System.Windows.Controls.InkCanvas>时<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>设置为<xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>。</span><span class="sxs-lookup"><span data-stu-id="4422b-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4422b-105">示例</span><span class="sxs-lookup"><span data-stu-id="4422b-105">Example</span></span>  
 <span data-ttu-id="4422b-106">以下示例创建自定义控件，使用户能够擦除部分笔画。</span><span class="sxs-lookup"><span data-stu-id="4422b-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="4422b-107">此示例创建包含手写内容时进行初始化的控件。</span><span class="sxs-lookup"><span data-stu-id="4422b-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="4422b-108">若要创建收集墨迹的控件，请参阅[创建墨迹输入控件](creating-an-ink-input-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4422b-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
