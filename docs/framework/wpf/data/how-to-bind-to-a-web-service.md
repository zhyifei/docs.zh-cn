---
title: "如何：绑定到 Web 服务"
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
- binding data [WPF], Web service
- Web service binding [WPF]
- data binding [WPF], Web service
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d1b81949d6d91420c828564debd311af47dfdfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-web-service"></a><span data-ttu-id="ec583-102">如何：绑定到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="ec583-102">How to: Bind to a Web Service</span></span>
<span data-ttu-id="ec583-103">此示例演示如何将绑定到 Web 服务方法调用返回的对象。</span><span class="sxs-lookup"><span data-stu-id="ec583-103">This example shows how to bind to objects returned by Web service method calls.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec583-104">示例</span><span class="sxs-lookup"><span data-stu-id="ec583-104">Example</span></span>  
 <span data-ttu-id="ec583-105">此示例使用[MSDN/TechNet 发布系统 (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677)检索支持指定的文档的语言的列表。</span><span class="sxs-lookup"><span data-stu-id="ec583-105">This example uses the [MSDN/TechNet Publishing System (MTPS) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677) to retrieve the list of languages supported by a specified document.</span></span>  
  
 <span data-ttu-id="ec583-106">在调用 Web 服务之前，你需要创建对它的引用。</span><span class="sxs-lookup"><span data-stu-id="ec583-106">Before you call a Web service, you need to create a reference to it.</span></span> <span data-ttu-id="ec583-107">若要创建对 MTPS 服务使用的 Web 引用[!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ec583-107">To create a Web reference to the MTPS service using [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], follow the following steps:</span></span>  
  
1.  <span data-ttu-id="ec583-108">打开你的项目中[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ec583-108">Open your project in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="ec583-109">从**项目**菜单上，单击**添加 Web 引用**。</span><span class="sxs-lookup"><span data-stu-id="ec583-109">From the **Project** menu, click **Add Web Reference**.</span></span>  
  
3.  <span data-ttu-id="ec583-110">在对话框中，设置**URL**到[http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)。</span><span class="sxs-lookup"><span data-stu-id="ec583-110">In the dialog box, set the **URL** to [http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl).</span></span>  
  
4.  <span data-ttu-id="ec583-111">按**转**然后**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="ec583-111">Press **Go** and then **Add Reference**.</span></span>  
  
 <span data-ttu-id="ec583-112">接下来，调用 Web 服务方法并设置<xref:System.Windows.FrameworkElement.DataContext%2A>相应的控件或返回的对象的窗口。</span><span class="sxs-lookup"><span data-stu-id="ec583-112">Next, you call the Web service method and set the <xref:System.Windows.FrameworkElement.DataContext%2A> of the appropriate control or window to the returned object.</span></span> <span data-ttu-id="ec583-113">**GetContent** MTPS 服务的方法会引用**getContentRequest**对象。</span><span class="sxs-lookup"><span data-stu-id="ec583-113">The **GetContent** method of the MTPS service takes a reference to the **getContentRequest** object.</span></span> <span data-ttu-id="ec583-114">因此，下面的示例首先设置的请求对象：</span><span class="sxs-lookup"><span data-stu-id="ec583-114">Therefore, the following example first sets up a request object:</span></span>  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <span data-ttu-id="ec583-115">后<xref:System.Windows.FrameworkElement.DataContext%2A>已设置，你可以创建到该对象的属性的绑定，<xref:System.Windows.FrameworkElement.DataContext%2A>已设置为。</span><span class="sxs-lookup"><span data-stu-id="ec583-115">After the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set, you can create bindings to the properties of the object that the <xref:System.Windows.FrameworkElement.DataContext%2A> has been set to.</span></span> <span data-ttu-id="ec583-116">在此示例中，<xref:System.Windows.FrameworkElement.DataContext%2A>设置为**getContentResponse**返回对象**GetContent**方法。</span><span class="sxs-lookup"><span data-stu-id="ec583-116">In this example, the <xref:System.Windows.FrameworkElement.DataContext%2A> is set to the **getContentResponse** object returned by the **GetContent** method.</span></span> <span data-ttu-id="ec583-117">在下面的示例中，<xref:System.Windows.Controls.ItemsControl>将绑定到并显示**区域设置**值**availableVersionsAndLocales**的**getContentResponse**。</span><span class="sxs-lookup"><span data-stu-id="ec583-117">In the following example, the <xref:System.Windows.Controls.ItemsControl> binds to and displays the **locale** values of **availableVersionsAndLocales** of **getContentResponse**.</span></span>  
  
 [!code-xaml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 <span data-ttu-id="ec583-118">有关的结构信息**getContentResponse**，请参阅[内容服务文档](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx)。</span><span class="sxs-lookup"><span data-stu-id="ec583-118">For information about the structure of **getContentResponse**, see [Content Service documentation](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec583-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec583-119">See Also</span></span>  
 [<span data-ttu-id="ec583-120">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="ec583-120">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ec583-121">绑定源概述</span><span class="sxs-lookup"><span data-stu-id="ec583-121">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="ec583-122">让数据可供 XAML 中的绑定使用</span><span class="sxs-lookup"><span data-stu-id="ec583-122">Make Data Available for Binding in XAML</span></span>](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)
