---
title: "如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], binding to XDocument
- data binding [WPF], binding to XElement
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6b39c45a7c85155a0fb46e8e176da5979e52e6e1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results"></a>如何：绑定到 XDocument、XElement 或 LINQ for XML 查询结果
此示例演示如何将绑定到的 XML 数据<xref:System.Windows.Controls.ItemsControl>使用<xref:System.Xml.Linq.XDocument>。  
  
## <a name="example"></a>示例  
 下面的 XAML 代码定义<xref:System.Windows.Controls.ItemsControl>并包含类型的数据的数据模板`Planet`中`http://planetsNS`XML 命名空间。 占用命名空间的 XML 数据类型必须包含相应的命名空间（用大括号括起来），并且如果它出现在 XAML 标记扩展可能出现的位置，则还必须在相应命名空间前加上大括号转义序列。 此代码将绑定到动态属性对应于<xref:System.Xml.Linq.XContainer.Element%2A>和<xref:System.Xml.Linq.XElement.Attribute%2A>方法<xref:System.Xml.Linq.XElement>类。 借助动态属性，XAML 可以绑定到共享方法名称的动态属性。 有关详细信息，请参阅 [LINQ to XML 动态属性](/visualstudio/designers/linq-to-xml-dynamic-properties)。 请注意 XML 的默认命名空间声明为何不适用于特性名。  
  
 [!code-xaml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xaml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 下面的 C# 代码调用<xref:System.Xml.Linq.XDocument.Load%2A>堆栈面板数据上下文设置为的名为的元素的所有子元素和`SolarSystemPlanets`中`http://planetsNS`XML 命名空间。  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML 数据可以存储为 XAML 资源使用<xref:System.Windows.Data.ObjectDataProvider>。 有关完整示例，请参阅 [L2DBForm.xaml 源代码](http://msdn.microsoft.com/library/624e96d4-6d27-4195-8ac2-2f3835f6c57e)。 下面的示例演示代码如何将数据上下文设置为对象资源。  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 将映射到的动态属性<xref:System.Xml.Linq.XContainer.Element%2A>和<xref:System.Xml.Linq.XElement.Attribute%2A>提供在 XAML 中的灵活性。 代码还可以绑定到 LINQ for XML 查询的结果。 此示例绑定到按元素值排序的查询结果。  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## <a name="see-also"></a>另请参阅  
 [绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [使用 LINQ to XML 进行 WPF 数据绑定概述](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)  
 [使用 LINQ to XML 的 WPF 数据绑定示例](/visualstudio/designers/wpf-data-binding-using-linq-to-xml-example)  
 [LINQ to XML 动态属性](/visualstudio/designers/linq-to-xml-dynamic-properties)
