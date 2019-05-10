---
title: 如何：使用控件呈现类
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- professional appearance [Windows Forms], rendering Windows Forms controls
- visual themes [Windows Forms], applying to Windows Forms controls
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
ms.openlocfilehash: a0f450ff5f169026007002a0d2907ee35e79b29d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630553"
---
# <a name="how-to-use-a-control-rendering-class"></a><span data-ttu-id="78676-102">如何：使用控件呈现类</span><span class="sxs-lookup"><span data-stu-id="78676-102">How to: Use a Control Rendering Class</span></span>
<span data-ttu-id="78676-103">此示例演示如何使用<xref:System.Windows.Forms.ComboBoxRenderer>类呈现的下拉箭头的组合框控件。</span><span class="sxs-lookup"><span data-stu-id="78676-103">This example demonstrates how to use the <xref:System.Windows.Forms.ComboBoxRenderer> class to render the drop-down arrow of a combo box control.</span></span> <span data-ttu-id="78676-104">此示例由<xref:System.Windows.Forms.Control.OnPaint%2A>简单的自定义控件的方法。</span><span class="sxs-lookup"><span data-stu-id="78676-104">The example consists of the <xref:System.Windows.Forms.Control.OnPaint%2A> method of a simple custom control.</span></span> <span data-ttu-id="78676-105"><xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType>属性用于确定是否在应用程序窗口的工作区中启用了可视样式。</span><span class="sxs-lookup"><span data-stu-id="78676-105">The <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=nameWithType> property is used to determine whether visual styles are enabled in the client area of application windows.</span></span> <span data-ttu-id="78676-106">如果视觉样式已处于活动状态，则<xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType>方法将呈现的下拉箭头以视觉样式; 否则为<xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType>方法将呈现中的经典 Windows 样式的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="78676-106">If visual styles are active, then the <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=nameWithType> method will render the drop-down arrow with visual styles; otherwise, the <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=nameWithType> method will render the drop-down arrow in the classic Windows style.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78676-107">示例</span><span class="sxs-lookup"><span data-stu-id="78676-107">Example</span></span>  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="78676-108">编译代码</span><span class="sxs-lookup"><span data-stu-id="78676-108">Compiling the Code</span></span>  
 <span data-ttu-id="78676-109">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="78676-109">This example requires:</span></span>  
  
- <span data-ttu-id="78676-110">自定义控件派生自<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="78676-110">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
- <span data-ttu-id="78676-111">一个<xref:System.Windows.Forms.Form>承载自定义控件。</span><span class="sxs-lookup"><span data-stu-id="78676-111">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
- <span data-ttu-id="78676-112">对引用<xref:System?displayProperty=nameWithType>， <xref:System.Drawing?displayProperty=nameWithType>， <xref:System.Windows.Forms?displayProperty=nameWithType>，和<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="78676-112">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78676-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="78676-113">See also</span></span>

- [<span data-ttu-id="78676-114">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="78676-114">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
