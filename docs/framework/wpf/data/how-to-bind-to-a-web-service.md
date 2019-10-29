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
ms.openlocfilehash: d752f4815de16daa466302881116e80aceec6edf
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040905"
---
# <a name="how-to-bind-to-a-web-service"></a>如何：绑定到 Web 服务
此示例演示如何绑定到由 Web 服务方法调用返回的对象。  
  
## <a name="example"></a>示例  
 此示例使用[MSDN/TechNet 发布系统（MTPS）内容服务](https://go.microsoft.com/fwlink/?LinkId=95677)检索指定文档支持的语言列表。  
  
 在调用 Web 服务之前，需要创建对它的引用。 若要使用 Visual Studio 创建对 MTPS 服务的 Web 引用，请执行以下步骤：  
  
1. 在 Visual Studio 中打开项目。  
  
2. 从 "**项目**" 菜单中，单击 "**添加 Web 引用**"。  
  
3. 在对话框中，将**URL**设置为[http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)。  
  
4. 按 "**开始**"，然后单击 "**添加引用**"。  
  
 接下来，将调用 Web 服务方法，并将相应控件或窗口的 <xref:System.Windows.FrameworkElement.DataContext%2A> 设置为返回的对象。 MTPS 服务的 `GetContent` 方法采用对 `getContentRequest` 对象的引用。 因此，以下示例首先设置 request 对象：  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 设置 <xref:System.Windows.FrameworkElement.DataContext%2A> 后，可以创建对 <xref:System.Windows.FrameworkElement.DataContext%2A> 已设置为的对象的属性的绑定。 在此示例中，<xref:System.Windows.FrameworkElement.DataContext%2A> 设置为 `GetContent` 方法返回的 `getContentResponse` 对象。 在下面的示例中，<xref:System.Windows.Controls.ItemsControl> 绑定到，并显示 `getContentResponse``availableVersionsAndLocales` 的 `locale` 值。  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 有关 `getContentResponse`结构的信息，请参阅[内容服务文档](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)。  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](data-binding-overview.md)
- [绑定源概述](binding-sources-overview.md)
- [让数据可供 XAML 中的绑定使用](how-to-make-data-available-for-binding-in-xaml.md)
