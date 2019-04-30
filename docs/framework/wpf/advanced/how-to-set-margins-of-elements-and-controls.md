---
title: 如何：设置元素和控件的边距
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting [WPF], Margin property
- properties [WPF], Margin property
- Margin property [WPF], setting
ms.assetid: 70ebee01-6f87-4352-8dd4-402c65eaaed6
ms.openlocfilehash: 3263810806b6b4bbec15eadfd1f1da3a57d12698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052360"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="c34c2-102">如何：设置元素和控件的边距</span><span class="sxs-lookup"><span data-stu-id="c34c2-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="c34c2-103">此示例介绍了如何设置<xref:System.Windows.FrameworkElement.Margin%2A>属性，通过更改在代码隐藏中的边距的任何现有属性值。</span><span class="sxs-lookup"><span data-stu-id="c34c2-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="c34c2-104"><xref:System.Windows.FrameworkElement.Margin%2A>属性是属性的<xref:System.Windows.FrameworkElement>基元素，并因此由各种控件和其他元素继承。</span><span class="sxs-lookup"><span data-stu-id="c34c2-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="c34c2-105">此示例用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，使用代码隐藏文件[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]引用。</span><span class="sxs-lookup"><span data-stu-id="c34c2-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="c34c2-106">代码隐藏显示在C#和 Microsoft Visual Basic 版本。</span><span class="sxs-lookup"><span data-stu-id="c34c2-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c34c2-107">示例</span><span class="sxs-lookup"><span data-stu-id="c34c2-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
