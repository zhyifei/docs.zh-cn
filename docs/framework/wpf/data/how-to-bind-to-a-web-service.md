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
ms.openlocfilehash: b2ef0cce293913fc7bd9d59baa91bd875823cbe2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353928"
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="db2b4-102">如何：绑定到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="db2b4-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="db2b4-103">此示例演示如何将绑定到由 Web 服务方法调用返回的对象。</span><span class="sxs-lookup"><span data-stu-id="db2b4-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db2b4-104">示例</span><span class="sxs-lookup"><span data-stu-id="db2b4-104">Example</span></span>  
 <span data-ttu-id="db2b4-105">此示例使用[MSDN/TechNet 发布系统 (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677)检索支持指定的文档的语言的列表。</span><span class="sxs-lookup"><span data-stu-id="db2b4-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](https://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="db2b4-106">在调用 Web 服务之前，需要创建对它的引用。</span><span class="sxs-lookup"><span data-stu-id="db2b4-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="db2b4-107">若要创建对 MTPS 服务使用的 Web 引用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="db2b4-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="db2b4-108">在 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 中打开项目。</span><span class="sxs-lookup"><span data-stu-id="db2b4-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="db2b4-109">从**项目**菜单上，单击**添加 Web 引用**。</span><span class="sxs-lookup"><span data-stu-id="db2b4-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="db2b4-110">在对话框中，将 **URL** 设置为 [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)。</span><span class="sxs-lookup"><span data-stu-id="db2b4-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](https://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="db2b4-111">按“转到”，然后按“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="db2b4-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="db2b4-112">接下来，调用 Web 服务方法并将相应控件或窗口的 <xref:System.Windows.FrameworkElement.DataContext%2A> 设置为返回的对象。</span><span class="sxs-lookup"><span data-stu-id="db2b4-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="db2b4-113">MTPS 服务的  **GetContent** 方法将引用 **getContentRequest** 对象。</span><span class="sxs-lookup"><span data-stu-id="db2b4-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="db2b4-114">因此，下面的示例首先设置请求对象：</span><span class="sxs-lookup"><span data-stu-id="db2b4-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="db2b4-115"><xref:System.Windows.FrameworkElement.DataContext%2A> 设置完成后，即可创建对特定对象（已将 <xref:System.Windows.FrameworkElement.DataContext%2A> 设置为此对象）的属性的绑定。</span><span class="sxs-lookup"><span data-stu-id="db2b4-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="db2b4-116">在此示例中，<xref:System.Windows.FrameworkElement.DataContext%2A> 设置为 **GetContent** 方法返回的 **getContentResponse** 对象。</span><span class="sxs-lookup"><span data-stu-id="db2b4-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="db2b4-117">在以下示例中，<xref:System.Windows.Controls.ItemsControl> 绑定到 **getContentResponse** 的 **availableVersionsAndLocales** 的 **locale** 值并显示这些值。</span><span class="sxs-lookup"><span data-stu-id="db2b4-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="db2b4-118">有关 **getContentResponse** 结构的信息，请参阅[内容服务文档](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx)。</span><span class="sxs-lookup"><span data-stu-id="db2b4-118">For information about the structure of **getContentResponse**, see [Content Service documentation](https://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2b4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="db2b4-119">See also</span></span>
- [<span data-ttu-id="db2b4-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="db2b4-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="db2b4-121">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="db2b4-121">Binding Sources Overview</span></span>](binding-sources-overview.md)
- [<span data-ttu-id="db2b4-122">让数据可供 XAML 中的绑定使用</span><span class="sxs-lookup"><span data-stu-id="db2b4-122">Make Data Available for Binding in XAML</span></span>](how-to-make-data-available-for-binding-in-xaml.md)
