---
title: 如何：绑定到 Web 服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
ms.openlocfilehash: 84c5aee8d2bc7d31ebcfee98930d9a0847c527d5
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576793"
---
# <a name="how-to-bind-to-a-web-service"></a>如何：绑定到 Web 服务
此示例演示如何将绑定到由 Web 服务方法调用返回的对象。  
  
## <a name="example"></a>示例  
 此示例使用[MSDN/TechNet 发布系统 (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677)检索支持指定的文档的语言的列表。  
  
 在调用 Web 服务之前，需要创建对它的引用。 若要创建对 MTPS 服务使用的 Web 引用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，请执行以下步骤：  
  
1.  打开的项目中[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]。  
  
2.  从**项目**菜单上，单击**添加 Web 引用**。  
  
3.  在对话框中，将**URL**到[ http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl ](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)。  
  
4.  按**转**，然后**添加引用**。  
  
 接下来，调用 Web 服务方法并设置<xref:System.Windows.FrameworkElement.DataContext%2A>的相应的控件或窗口中返回的对象。 **GetContent** MTPS 服务的方法将引用**getContentRequest**对象。 因此，下面的示例首先设置请求对象：  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 之后<xref:System.Windows.FrameworkElement.DataContext%2A>已设置，您可以创建到该对象的属性的绑定的<xref:System.Windows.FrameworkElement.DataContext%2A>已设置为。 在此示例中，<xref:System.Windows.FrameworkElement.DataContext%2A>设置为**getContentResponse**返回的对象**GetContent**方法。 在以下示例中，<xref:System.Windows.Controls.ItemsControl>绑定到并显示**区域设置**的值**availableVersionsAndLocales**的**getContentResponse**。  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 有关结构的信息**getContentResponse**，请参阅[内容服务文档](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)。  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [让数据可供 XAML 中的绑定使用](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
