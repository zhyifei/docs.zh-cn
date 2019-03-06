---
title: 如何：使用 FontSizeConverter 类
ms.date: 03/30/2017
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
ms.openlocfilehash: 21050ae69ad834b56c70f40d85138714af334dab
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364094"
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="b57f3-102">如何：使用 FontSizeConverter 类</span><span class="sxs-lookup"><span data-stu-id="b57f3-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="b57f3-103">示例</span><span class="sxs-lookup"><span data-stu-id="b57f3-103">Example</span></span>  
 <span data-ttu-id="b57f3-104">此示例演示如何创建的实例<xref:System.Windows.FontSizeConverter>并使用它来更改字体大小。</span><span class="sxs-lookup"><span data-stu-id="b57f3-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="b57f3-105">该示例定义一个名为的自定义方法`changeSize`的内容的转换<xref:System.Windows.Controls.ListBoxItem>在单独的定义，[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]的实例的文件， <xref:System.Double>，然后再转换<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="b57f3-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="b57f3-106">此方法将传递<xref:System.Windows.Controls.ListBoxItem>到<xref:System.Windows.FontSizeConverter>对象，它将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>的实例<xref:System.Double>。</span><span class="sxs-lookup"><span data-stu-id="b57f3-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="b57f3-107">然后将此值传递的值为<xref:System.Windows.Controls.TextBlock.FontSize%2A>属性的<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="b57f3-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="b57f3-108">此示例还定义调用的第二个自定义方法`changeFamily`。</span><span class="sxs-lookup"><span data-stu-id="b57f3-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="b57f3-109">此方法将转换<xref:System.Windows.Controls.ContentControl.Content%2A>的<xref:System.Windows.Controls.ListBoxItem>到<xref:System.String>，然后将传递到该值<xref:System.Windows.Controls.TextBlock.FontFamily%2A>属性<xref:System.Windows.Controls.TextBlock>元素。</span><span class="sxs-lookup"><span data-stu-id="b57f3-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="b57f3-110">此示例不运行。</span><span class="sxs-lookup"><span data-stu-id="b57f3-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](~/samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b57f3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b57f3-111">See also</span></span>
- <xref:System.Windows.FontSizeConverter>
