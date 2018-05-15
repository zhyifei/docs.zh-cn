---
title: 如何：使数据可用于 XAML 中的绑定
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: dd66fb2f96f8c42fea36afaeda0aaf35a2adbace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="f0cb5-102">如何：使数据可用于 XAML 中的绑定</span><span class="sxs-lookup"><span data-stu-id="f0cb5-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="f0cb5-103">本主题讨论您可以使数据可用于在绑定的不同方式[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，取决于你的应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-103">This topic discusses the different ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0cb5-104">示例</span><span class="sxs-lookup"><span data-stu-id="f0cb5-104">Example</span></span>  
 <span data-ttu-id="f0cb5-105">如果你有[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象你想要将绑定到中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以使该对象可绑定是定义为资源并为其提供的一种方法`x:Key`。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="f0cb5-106">在下面的示例中，你有`Person`具有名为的字符串属性对象`PersonName`。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="f0cb5-107">`Person`对象，用突出显示的行将包含显示`<src>`调用的命名空间中定义了元素， `SDKSample`。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-107">The `Person` object, which is shown by the highlighted line that contains the `<src>` element, is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="f0cb5-108">你可以随后可以绑定<xref:System.Windows.Controls.TextBlock>到中的对象的控件[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，如突出显示的行包含`<TextBlock>`元素所示。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="f0cb5-109">或者，可以使用<xref:System.Windows.Data.ObjectDataProvider>类，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f0cb5-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="f0cb5-110">定义绑定一样，突出显示的行将包含`<TextBlock>`元素所示。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="f0cb5-111">在此特定示例中，结果是相同的： 必须<xref:System.Windows.Controls.TextBlock>的文本内容与`Joe`。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="f0cb5-112">但是，<xref:System.Windows.Data.ObjectDataProvider>类提供如能够绑定到方法的结果的功能。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="f0cb5-113">你可以选择使用<xref:System.Windows.Data.ObjectDataProvider>类如果你需要它提供的功能。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="f0cb5-114">但是，如果你正在绑定到已创建的对象，你需要设置`DataContext`在代码中，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="f0cb5-115">访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.XmlDataProvider>类，请参阅[将绑定到 XML 数据使用 XPath 查询和 XMLDataProvider](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="f0cb5-116">访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.ObjectDataProvider>类，请参阅[XML 查询结果绑定到 XDocument、 XElement 或 LINQ](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="f0cb5-117">你可以指定要绑定到的数据的不同方法的信息，请参阅[指定绑定源](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-117">For information about the different ways you can specify the data you are binding to, see [Specify the Binding Source](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="f0cb5-118">有关可以绑定到哪些类型的数据或实现你自己的方式信息[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象的绑定，请参阅[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="f0cb5-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](../../../../docs/framework/wpf/data/binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0cb5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0cb5-119">See Also</span></span>  
 [<span data-ttu-id="f0cb5-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="f0cb5-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="f0cb5-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="f0cb5-121">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
