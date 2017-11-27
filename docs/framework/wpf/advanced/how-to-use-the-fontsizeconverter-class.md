---
title: "如何：使用 FontSizeConverter 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcf2d7348ca5b6b9d3b2edc44f92afbd46d32594
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="ae4d4-102">如何：使用 FontSizeConverter 类</span><span class="sxs-lookup"><span data-stu-id="ae4d4-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="ae4d4-103">示例</span><span class="sxs-lookup"><span data-stu-id="ae4d4-103">Example</span></span>  
 <span data-ttu-id="ae4d4-104">此示例演示如何创建的实例<xref:System.Windows.FontSizeConverter>并使用它来将字体大小更改。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="ae4d4-105">该示例定义的自定义的方法调用`changeSize`，用于将转换的内容<xref:System.Windows.Controls.ListBoxItem>，如在单独定义[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件、 实例<xref:System.Double>，然后再转换<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="ae4d4-106">此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.FontSizeConverter>对象，后者将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到实例<xref:System.Double>。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="ae4d4-107">此值然后传递的值作为<xref:System.Windows.Controls.TextBlock.FontSize%2A>属性<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="ae4d4-108">此示例还定义称为的第二个自定义方法`changeFamily`。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="ae4d4-109">此方法将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到<xref:System.String>，然后将传递到该值<xref:System.Windows.Controls.TextBlock.FontFamily%2A>属性<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="ae4d4-110">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="ae4d4-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ae4d4-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae4d4-111">See Also</span></span>  
 <xref:System.Windows.FontSizeConverter>
