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
ms.openlocfilehash: 41a0f1d025061cc7c1472a831fbbd5ed2f01b043
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543645"
---
# <a name="how-to-set-margins-of-elements-and-controls"></a><span data-ttu-id="7f23c-102">如何：设置元素和控件的边距</span><span class="sxs-lookup"><span data-stu-id="7f23c-102">How to: Set Margins of Elements and Controls</span></span>
<span data-ttu-id="7f23c-103">本示例介绍了如何设置<xref:System.Windows.FrameworkElement.Margin%2A>属性，通过更改的代码隐藏文件中的边距任何现有属性值。</span><span class="sxs-lookup"><span data-stu-id="7f23c-103">This example describes how to set the <xref:System.Windows.FrameworkElement.Margin%2A> property, by changing any existing property value for the margin in code-behind.</span></span> <span data-ttu-id="7f23c-104"><xref:System.Windows.FrameworkElement.Margin%2A>属性是属性的<xref:System.Windows.FrameworkElement>基元素，并因此由各种控件和其他元素继承。</span><span class="sxs-lookup"><span data-stu-id="7f23c-104">The <xref:System.Windows.FrameworkElement.Margin%2A> property is a property of the <xref:System.Windows.FrameworkElement> base element, and is thus inherited by a variety of controls and other elements.</span></span>  
  
 <span data-ttu-id="7f23c-105">此示例用编写[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，与隐藏代码文件[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]引用。</span><span class="sxs-lookup"><span data-stu-id="7f23c-105">This example is written in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], with a code-behind file that the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] refers to.</span></span> <span data-ttu-id="7f23c-106">代码隐藏所示的 C# 和 Microsoft Visual Basic 版本。</span><span class="sxs-lookup"><span data-stu-id="7f23c-106">The code-behind is shown in both a C# and a Microsoft Visual Basic version.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f23c-107">示例</span><span class="sxs-lookup"><span data-stu-id="7f23c-107">Example</span></span>  
 [!code-xaml[FEMarginProgrammatic#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FEMarginProgrammatic#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEMarginProgrammatic/CSharp/default.xaml.cs#handler)]
 [!code-vb[FEMarginProgrammatic#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEMarginProgrammatic/VisualBasic/default.xaml.vb#handler)]
