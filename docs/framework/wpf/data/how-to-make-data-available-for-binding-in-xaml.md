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
ms.openlocfilehash: 91e89dbf36024c31f4afcd9b6d956944baf13576
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174181"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="707f0-102">如何：使数据可用于 XAML 中的绑定</span><span class="sxs-lookup"><span data-stu-id="707f0-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="707f0-103">本主题讨论各种方法，您可以根据应用程序的需求将数据可用于绑定[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="707f0-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="707f0-104">示例</span><span class="sxs-lookup"><span data-stu-id="707f0-104">Example</span></span>  
 <span data-ttu-id="707f0-105">如果您有一个公用语言运行时 （CLR） 对象，您希望绑定[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]到 ，使对象可用于绑定的一种方法是将其定义为资源并给它一个`x:Key`。</span><span class="sxs-lookup"><span data-stu-id="707f0-105">If you have a common language runtime (CLR) object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="707f0-106">在下面的示例中，您有一个`Person`具有字符串属性的对象， `PersonName`</span><span class="sxs-lookup"><span data-stu-id="707f0-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="707f0-107">对象`Person`（在显示的突出显示包含`<src>`元素的行中）在称为`SDKSample`的命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="707f0-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="707f0-108">然后，<xref:System.Windows.Controls.TextBlock>可以将控件绑定到 中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]的对象，如包含`<TextBlock>`元素的突出显示行所示。</span><span class="sxs-lookup"><span data-stu-id="707f0-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span>
  
 <span data-ttu-id="707f0-109">或者，您可以使用类<xref:System.Windows.Data.ObjectDataProvider>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="707f0-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="707f0-110">定义绑定的方式与包含`<TextBlock>`元素的突出显示行相同。</span><span class="sxs-lookup"><span data-stu-id="707f0-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="707f0-111">在此特定示例中，结果相同：您<xref:System.Windows.Controls.TextBlock>具有 与 文本内容`Joe`一起 。</span><span class="sxs-lookup"><span data-stu-id="707f0-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="707f0-112">但是，类<xref:System.Windows.Data.ObjectDataProvider>提供的功能，例如绑定到方法结果的功能。</span><span class="sxs-lookup"><span data-stu-id="707f0-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="707f0-113">如果需要提供的功能，<xref:System.Windows.Data.ObjectDataProvider>可以选择使用该类。</span><span class="sxs-lookup"><span data-stu-id="707f0-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="707f0-114">但是，如果要绑定到已创建的对象，则需要设置`DataContext`in 代码，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="707f0-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="707f0-115">要使用<xref:System.Windows.Data.XmlDataProvider>类访问 XML 数据以进行绑定，请参阅[使用 XMLData 提供程序和 XPath 查询绑定到 XML 数据](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="707f0-115">To access XML data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="707f0-116">要使用 类访问用于绑定的<xref:System.Windows.Data.ObjectDataProvider>XML 数据，请参阅[绑定到 XDocument、XElement 或 LINQ 获取 XML 查询结果](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。</span><span class="sxs-lookup"><span data-stu-id="707f0-116">To access XML data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="707f0-117">有关指定绑定数据的许多方法的信息，请参阅[指定绑定源](how-to-specify-the-binding-source.md)。</span><span class="sxs-lookup"><span data-stu-id="707f0-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="707f0-118">有关可以绑定到哪些类型的数据以及如何实现自己的通用语言运行时 （CLR） 对象进行绑定的信息，请参阅[绑定源概述](binding-sources-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="707f0-118">For information about what types of data you can bind to or how to implement your own common language runtime (CLR) objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="707f0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="707f0-119">See also</span></span>

- [<span data-ttu-id="707f0-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="707f0-120">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="707f0-121">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="707f0-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
