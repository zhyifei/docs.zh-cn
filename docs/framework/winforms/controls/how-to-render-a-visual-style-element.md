---
title: 如何：呈现视觉样式元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- visual themes [Windows Forms], applying to elements of Windows Forms applications
- professional appearance [Windows Forms], applying to elements of Windows Forms applications
- visual styles [Windows Forms], rendering Windows Forms controls
ms.assetid: a207781b-1baa-4ce9-b788-1e951bd4b5df
ms.openlocfilehash: 57c2bc5722f77338225d70b514345344211656dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59312392"
---
# <a name="how-to-render-a-visual-style-element"></a><span data-ttu-id="33091-102">如何：呈现视觉样式元素</span><span class="sxs-lookup"><span data-stu-id="33091-102">How to: Render a Visual Style Element</span></span>
<span data-ttu-id="33091-103"><xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>命名空间公开了<xref:System.Windows.Forms.VisualStyles.VisualStyleElement>对象，后者表示 Windows 用户界面 (UI) 元素支持的视觉样式。</span><span class="sxs-lookup"><span data-stu-id="33091-103">The <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespace exposes <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> objects that represent the Windows user interface (UI) elements supported by visual styles.</span></span> <span data-ttu-id="33091-104">本主题演示如何使用<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>类来呈现<xref:System.Windows.Forms.VisualStyles.VisualStyleElement>，它表示**注销**并**关机**开始菜单的按钮。</span><span class="sxs-lookup"><span data-stu-id="33091-104">This topic demonstrates how to use the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> class to render the <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> that represents the **Log Off** and **Shut Down** buttons of the Start menu.</span></span>  
  
### <a name="to-render-a-visual-style-element"></a><span data-ttu-id="33091-105">若要呈现的视觉样式元素</span><span class="sxs-lookup"><span data-stu-id="33091-105">To render a visual style element</span></span>  
  
1. <span data-ttu-id="33091-106">创建<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>并将其设置为想要绘制的元素。</span><span class="sxs-lookup"><span data-stu-id="33091-106">Create a <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> and set it to the element you want to draw.</span></span> <span data-ttu-id="33091-107">请注意，使用<xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType>属性和<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType>方法;<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A>构造函数将引发异常，如果禁用了视觉样式，或者元素未定义。</span><span class="sxs-lookup"><span data-stu-id="33091-107">Note the use of the <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A?displayProperty=nameWithType> property and the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.IsElementDefined%2A?displayProperty=nameWithType> method; the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor%2A> constructor will throw an exception if visual styles are disabled or an element is undefined.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#4)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#4)]  
  
2. <span data-ttu-id="33091-108">调用<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A>方法来呈现元素<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>当前表示。</span><span class="sxs-lookup"><span data-stu-id="33091-108">Call the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.DrawBackground%2A> method to render the element that the <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> currently represents.</span></span>  
  
     [!code-cpp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/cpp/form1.cpp#6)]
     [!code-csharp[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/CS/form1.cs#6)]
     [!code-vb[System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.VisualStyles.VisualStyleRenderer_Simple/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="33091-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="33091-109">Compiling the Code</span></span>  
 <span data-ttu-id="33091-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="33091-110">This example requires:</span></span>  
  
-   <span data-ttu-id="33091-111">自定义控件派生自<xref:System.Windows.Forms.Control>类。</span><span class="sxs-lookup"><span data-stu-id="33091-111">A custom control derived from the <xref:System.Windows.Forms.Control> class.</span></span>  
  
-   <span data-ttu-id="33091-112">一个<xref:System.Windows.Forms.Form>承载自定义控件。</span><span class="sxs-lookup"><span data-stu-id="33091-112">A <xref:System.Windows.Forms.Form> that hosts the custom control.</span></span>  
  
-   <span data-ttu-id="33091-113">对引用<xref:System?displayProperty=nameWithType>， <xref:System.Drawing?displayProperty=nameWithType>， <xref:System.Windows.Forms?displayProperty=nameWithType>，和<xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="33091-113">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Windows.Forms.VisualStyles?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33091-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="33091-114">See also</span></span>

- [<span data-ttu-id="33091-115">使用视觉样式呈现控件</span><span class="sxs-lookup"><span data-stu-id="33091-115">Rendering Controls with Visual Styles</span></span>](rendering-controls-with-visual-styles.md)
