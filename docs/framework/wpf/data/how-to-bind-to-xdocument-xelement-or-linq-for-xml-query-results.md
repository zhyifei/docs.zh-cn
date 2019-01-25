---
title: 如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
ms.openlocfilehash: 0d68eb40b60481709ff2852a643908025e2e43ed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512328"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a><span data-ttu-id="85d36-102">如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果</span><span class="sxs-lookup"><span data-stu-id="85d36-102">How to: Bind to XDocument, XElement, or LINQ for XML Query Results</span></span>
<span data-ttu-id="85d36-103">此示例演示如何将绑定到 XML 数据<xref:System.Windows.Controls.ItemsControl>使用<xref:System.Xml.Linq.XDocument>。</span><span class="sxs-lookup"><span data-stu-id="85d36-103">This example demonstrates how to bind XML data to an <xref:System.Windows.Controls.ItemsControl> using <xref:System.Xml.Linq.XDocument>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d36-104">示例</span><span class="sxs-lookup"><span data-stu-id="85d36-104">Example</span></span>  
 <span data-ttu-id="85d36-105">下面的 XAML 代码定义<xref:System.Windows.Controls.ItemsControl>和包含类型的数据的数据模板`Planet`中`http://planetsNS`XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="85d36-105">The following XAML code defines an <xref:System.Windows.Controls.ItemsControl> and includes a data template for data of type `Planet` in the `http://planetsNS` XML namespace.</span></span> <span data-ttu-id="85d36-106">占用命名空间的 XML 数据类型必须包含相应的命名空间（用大括号括起来），并且如果它出现在 XAML 标记扩展可能出现的位置，则还必须在相应命名空间前加上大括号转义序列。</span><span class="sxs-lookup"><span data-stu-id="85d36-106">An XML data type that occupies a namespace must include the namespace in braces, and if it appears where a XAML markup extension could appear, it must precede the namespace with a brace escape sequence.</span></span> <span data-ttu-id="85d36-107">此代码将绑定到动态属性对应于<xref:System.Xml.Linq.XContainer.Element%2A>并<xref:System.Xml.Linq.XElement.Attribute%2A>方法的<xref:System.Xml.Linq.XElement>类。</span><span class="sxs-lookup"><span data-stu-id="85d36-107">This code binds to dynamic properties that correspond to the <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> methods of the <xref:System.Xml.Linq.XElement> class.</span></span> <span data-ttu-id="85d36-108">借助动态属性，XAML 可以绑定到共享方法名称的动态属性。</span><span class="sxs-lookup"><span data-stu-id="85d36-108">Dynamic properties enable XAML to bind to dynamic properties that share the names of methods.</span></span> <span data-ttu-id="85d36-109">有关详细信息，请参阅 [LINQ to XML 动态属性](/visualstudio/designers/linq-to-xml-dynamic-properties)。</span><span class="sxs-lookup"><span data-stu-id="85d36-109">To learn more, see [LINQ to XML Dynamic Properties](/visualstudio/designers/linq-to-xml-dynamic-properties).</span></span> <span data-ttu-id="85d36-110">请注意 XML 的默认命名空间声明为何不适用于特性名。</span><span class="sxs-lookup"><span data-stu-id="85d36-110">Notice how the default namespace declaration for the XML does not apply to attribute names.</span></span>  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 <span data-ttu-id="85d36-111">下面的 C# 代码调用<xref:System.Xml.Linq.XDocument.Load%2A>并将堆叠面板数据上下文设置为所指定元素的所有子元素的`SolarSystemPlanets`中`http://planetsNS`XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="85d36-111">The following C# code calls <xref:System.Xml.Linq.XDocument.Load%2A> and sets the stack panel data context to all subelements of the element named `SolarSystemPlanets` in the `http://planetsNS` XML namespace.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 <span data-ttu-id="85d36-112">XML 数据可以存储为 XAML 资源使用<xref:System.Windows.Data.ObjectDataProvider>。</span><span class="sxs-lookup"><span data-stu-id="85d36-112">XML data can be stored as a XAML resource using <xref:System.Windows.Data.ObjectDataProvider>.</span></span> <span data-ttu-id="85d36-113">有关完整示例，请参阅 [L2DBForm.xaml 源代码](https://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e)。</span><span class="sxs-lookup"><span data-stu-id="85d36-113">For a complete example, see  [L2DBForm.xaml Source Code](https://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e).</span></span> <span data-ttu-id="85d36-114">下面的示例演示代码如何将数据上下文设置为对象资源。</span><span class="sxs-lookup"><span data-stu-id="85d36-114">The following sample shows how code can set the data context to an object resource.</span></span>  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <span data-ttu-id="85d36-115">将映射到的动态属性<xref:System.Xml.Linq.XContainer.Element%2A>和<xref:System.Xml.Linq.XElement.Attribute%2A>XAML 中非常灵活。</span><span class="sxs-lookup"><span data-stu-id="85d36-115">The dynamic properties that map to <xref:System.Xml.Linq.XContainer.Element%2A> and <xref:System.Xml.Linq.XElement.Attribute%2A> provide flexibility within XAML.</span></span> <span data-ttu-id="85d36-116">代码还可以绑定到 LINQ for XML 查询的结果。</span><span class="sxs-lookup"><span data-stu-id="85d36-116">Your code can also bind to the results of a LINQ for XML query.</span></span> <span data-ttu-id="85d36-117">此示例绑定到按元素值排序的查询结果。</span><span class="sxs-lookup"><span data-stu-id="85d36-117">This example binds to query results ordered by an element value.</span></span>  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a><span data-ttu-id="85d36-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="85d36-118">See also</span></span>
- [<span data-ttu-id="85d36-119">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="85d36-119">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)
- [<span data-ttu-id="85d36-120">使用 LINQ to XML 进行 WPF 数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="85d36-120">WPF Data Binding with LINQ to XML Overview</span></span>](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [<span data-ttu-id="85d36-121">使用 LINQ to XML 的 WPF 数据绑定示例</span><span class="sxs-lookup"><span data-stu-id="85d36-121">WPF Data Binding Using LINQ to XML Example</span></span>](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)
- [<span data-ttu-id="85d36-122">LINQ to XML 动态属性</span><span class="sxs-lookup"><span data-stu-id="85d36-122">LINQ to XML Dynamic Properties</span></span>](/visualstudio/designers/linq-to-xml-dynamic-properties)
