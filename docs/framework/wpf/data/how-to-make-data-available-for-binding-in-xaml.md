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
ms.openlocfilehash: 97e878e4932ca9122bf27f76c32d1a56e69f253a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740603"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="49684-102">如何：使数据可用于 XAML 中的绑定</span><span class="sxs-lookup"><span data-stu-id="49684-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="49684-103">本主题讨论在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中可用于绑定的各种方式，具体取决于应用程序的需求。</span><span class="sxs-lookup"><span data-stu-id="49684-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49684-104">示例</span><span class="sxs-lookup"><span data-stu-id="49684-104">Example</span></span>  
 <span data-ttu-id="49684-105">如果要从 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]绑定到公共语言运行时（CLR）对象，则可以将该对象定义为可用于绑定的一种方法是将其定义为资源，并为其指定一个 `x:Key`。</span><span class="sxs-lookup"><span data-stu-id="49684-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="49684-106">在下面的示例中，你有一个具有名为 `PersonName`的字符串属性的 `Person` 对象。</span><span class="sxs-lookup"><span data-stu-id="49684-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="49684-107">在名为 `SDKSample`的命名空间中定义了 `Person` 对象（在突出显示的包含 `<src>` 元素的行中）。</span><span class="sxs-lookup"><span data-stu-id="49684-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="49684-108">然后，可以将 <xref:System.Windows.Controls.TextBlock> 控件绑定到 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中的对象，如包含 `<TextBlock>` 元素的突出显示的行所示。</span><span class="sxs-lookup"><span data-stu-id="49684-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="49684-109">或者，可以使用 <xref:System.Windows.Data.ObjectDataProvider> 类，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="49684-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="49684-110">可以采用相同的方式定义绑定，如包含 `<TextBlock>` 元素的突出显示的行所示。</span><span class="sxs-lookup"><span data-stu-id="49684-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="49684-111">在此特定示例中，结果是相同的：具有文本内容 `Joe`的 <xref:System.Windows.Controls.TextBlock>。</span><span class="sxs-lookup"><span data-stu-id="49684-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="49684-112">不过，<xref:System.Windows.Data.ObjectDataProvider> 类提供了一些功能，例如可以绑定到方法的结果。</span><span class="sxs-lookup"><span data-stu-id="49684-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="49684-113">如果需要它提供的功能，则可以选择使用 <xref:System.Windows.Data.ObjectDataProvider> 类。</span><span class="sxs-lookup"><span data-stu-id="49684-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="49684-114">但是，如果要绑定到已创建的对象，则需要在代码中设置 `DataContext`，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="49684-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="49684-115">若要使用 <xref:System.Windows.Data.XmlDataProvider> 类访问用于绑定的 XML 数据，请参阅[使用 XMLDataProvider 和 XPath 查询绑定到 Xml 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="49684-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="49684-116">若要使用 <xref:System.Windows.Data.ObjectDataProvider> 类访问用于绑定的 XML 数据，请参阅[绑定到 XDocument、system.xml.linq.xelement> 或 LINQ FOR XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。</span><span class="sxs-lookup"><span data-stu-id="49684-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="49684-117">有关指定要绑定到的数据的多种方式的信息，请参阅[指定绑定源](how-to-specify-the-binding-source.md)。</span><span class="sxs-lookup"><span data-stu-id="49684-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="49684-118">有关可以绑定到的数据类型或者如何实现您自己的公共语言运行时（CLR）对象进行绑定的信息，请参阅[绑定源概述](binding-sources-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="49684-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49684-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="49684-119">See also</span></span>

- [<span data-ttu-id="49684-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="49684-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="49684-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="49684-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
