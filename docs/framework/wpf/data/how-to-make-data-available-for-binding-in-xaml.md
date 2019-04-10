---
title: 如何：让数据可供 XAML 中的绑定使用
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2d51f06da31482c46b04d1eb86172c3eda246c20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145361"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="a9dea-102">如何：让数据可供 XAML 中的绑定使用</span><span class="sxs-lookup"><span data-stu-id="a9dea-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="a9dea-103">本主题讨论使数据可用于 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 绑定的各种方法，取决于应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="a9dea-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9dea-104">示例</span><span class="sxs-lookup"><span data-stu-id="a9dea-104">Example</span></span>  
 <span data-ttu-id="a9dea-105">如果想通过 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 绑定到某个[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 对象，使该对象可用于绑定的一种方法是将其定义为资源并为其提供 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="a9dea-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="a9dea-106">以下示例中提供一个`Person`对象，它具有名为 `PersonName` 的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="a9dea-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="a9dea-107">`Person`对象 (在突出显示且包含 `<src>` 元素的行中) 在名为 `SDKSample` 的命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="a9dea-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="a9dea-108">然后就可以将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的对象，如突出显示的包含 `<TextBlock>` 元素的行所示。</span><span class="sxs-lookup"><span data-stu-id="a9dea-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="a9dea-109">或者，可以使用 <xref:System.Windows.Data.ObjectDataProvider> 类，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="a9dea-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="a9dea-110">以相同的方式定义绑定，如突出显示的包含 `<TextBlock>` 元素的行所示。</span><span class="sxs-lookup"><span data-stu-id="a9dea-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="a9dea-111">在此特定示例中，结果是相同的：<xref:System.Windows.Controls.TextBlock> 的文本内容为 `Joe`。</span><span class="sxs-lookup"><span data-stu-id="a9dea-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="a9dea-112">但是，<xref:System.Windows.Data.ObjectDataProvider> 类还提供了其他功能，例如能够绑定到方法的结果。</span><span class="sxs-lookup"><span data-stu-id="a9dea-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="a9dea-113">如果需要 <xref:System.Windows.Data.ObjectDataProvider> 类提供的功能，则可以选用它。</span><span class="sxs-lookup"><span data-stu-id="a9dea-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="a9dea-114">但是，如果要绑定到已创建的对象，则需要在代码中设置 `DataContext`，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a9dea-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="a9dea-115">若要使用 <xref:System.Windows.Data.XmlDataProvider> 类访问 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据以进行绑定，请参阅[使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="a9dea-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="a9dea-116">若要使用 <xref:System.Windows.Data.ObjectDataProvider> 类访问 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据以进行绑定，请参阅[绑定到 XDocument、XElement 或 LINQ for XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。</span><span class="sxs-lookup"><span data-stu-id="a9dea-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="a9dea-117">有关指定要绑定到的数据的多种方法的相关信息，请参阅[指定绑定源](how-to-specify-the-binding-source.md)。</span><span class="sxs-lookup"><span data-stu-id="a9dea-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="a9dea-118">有关可以绑定到哪些数据类型或如何实现你自己的[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 对象以进行绑定的相关信息，请参阅[绑定源概述](binding-sources-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a9dea-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dea-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9dea-119">See also</span></span>

- [<span data-ttu-id="a9dea-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="a9dea-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="a9dea-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="a9dea-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
