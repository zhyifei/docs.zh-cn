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
ms.openlocfilehash: 070f67f30613d4522a48e08fd1c208fbe5887525
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920114"
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果

此示例演示如何使用 <xref:System.Xml.Linq.XDocument>将 XML 数据绑定到 <xref:System.Windows.Controls.ItemsControl>。

## <a name="example"></a>示例

下面的 XAML 代码定义了一个 <xref:System.Windows.Controls.ItemsControl>，并包括 `http://planetsNS` XML 命名空间中 `Planet` 类型数据的数据模板。 占用命名空间的 XML 数据类型必须包含相应的命名空间（用大括号括起来），并且如果它出现在 XAML 标记扩展可能出现的位置，则还必须在相应命名空间前加上大括号转义序列。 此代码绑定到与 <xref:System.Xml.Linq.XElement> 类的 <xref:System.Xml.Linq.XContainer.Element%2A> 和 <xref:System.Xml.Linq.XElement.Attribute%2A> 方法相对应的动态属性。 借助动态属性，XAML 可以绑定到共享方法名称的动态属性。 若要了解详细信息，请参阅[LINQ to XML 动态属性](linq-to-xml-dynamic-properties.md)。 请注意 XML 的默认命名空间声明为何不适用于特性名。

[!code-xaml[XLinqExample#StackPanelResources](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]
[!code-xaml[XLinqExample#ItemsControl](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]

下面C#的代码调用<xref:System.Xml.Linq.XDocument.Load%2A>，并将堆栈面板数据上下文设置为`http://planetsNS`XML 命名空间中名为`SolarSystemPlanets`的元素的所有子元素。

[!code-csharp[XLinqExample#LoadDCFromFile](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
[!code-vb[XLinqExample#LoadDCFromFile](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]

可以使用 <xref:System.Windows.Data.ObjectDataProvider>将 XML 数据存储为 XAML 资源。 有关完整示例，请参阅[l2dbform.xaml。](l2dbform-xaml-source-code.md) 下面的示例演示代码如何将数据上下文设置为对象资源。

[!code-csharp[XLinqExample#LoadDCFromXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
[!code-vb[XLinqExample#LoadDCFromXAML](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]

映射到 <xref:System.Xml.Linq.XContainer.Element%2A> 和 <xref:System.Xml.Linq.XElement.Attribute%2A> 的动态属性在 XAML 内提供了灵活性。 代码还可以绑定到 LINQ for XML 查询的结果。 此示例绑定到按元素值排序的查询结果。

[!code-csharp[XLinqExample#BindToResults](~/samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
[!code-vb[XLinqExample#BindToResults](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]

## <a name="see-also"></a>请参阅

- [绑定源概述](binding-sources-overview.md)
- [使用 LINQ to XML 进行 WPF 数据绑定概述](wpf-data-binding-with-linq-to-xml-overview.md)
- [使用 LINQ to XML 的 WPF 数据绑定示例](linq-to-xml-data-binding-sample.md)
- [LINQ to XML 动态属性](linq-to-xml-dynamic-properties.md)
