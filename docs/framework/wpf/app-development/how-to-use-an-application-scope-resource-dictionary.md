---
title: "如何：使用应用程序范围的资源字典"
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
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 417fea4dcbb5a8d0a27f9605be19de5921aaf0ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="1f89d-102">如何：使用应用程序范围的资源字典</span><span class="sxs-lookup"><span data-stu-id="1f89d-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="1f89d-103">本示例显示如何定义和使用应用程序范围的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="1f89d-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1f89d-104">示例</span><span class="sxs-lookup"><span data-stu-id="1f89d-104">Example</span></span>  
 <span data-ttu-id="1f89d-105"><xref:System.Windows.Application>公开共享资源的应用程序作用域存储： <xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="1f89d-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="1f89d-106">默认情况下，<xref:System.Windows.Application.Resources%2A>属性初始化时使用的实例<xref:System.Windows.ResourceDictionary>类型。</span><span class="sxs-lookup"><span data-stu-id="1f89d-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="1f89d-107">获取和设置使用的应用程序作用域属性时使用此实例<xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="1f89d-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="1f89d-108">有关详细信息，请参阅[如何： 获取和设置应用程序作用域资源](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095)。</span><span class="sxs-lookup"><span data-stu-id="1f89d-108">For more information, see [How to: Get and Set an Application-Scope Resource](http://msdn.microsoft.com/en-us/39e0420c-c9fc-47dc-8956-fdd95b214095).</span></span>
  
 <span data-ttu-id="1f89d-109">如果你有使用设置的多个资源<xref:System.Windows.Application.Resources%2A>，则可以使用自定义资源字典来存储这些资源和设置<xref:System.Windows.Application.Resources%2A>与之相反。</span><span class="sxs-lookup"><span data-stu-id="1f89d-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="1f89d-110">下图显示如何声明使用 XAML 的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="1f89d-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="1f89d-111">交换使用的整个资源字典<xref:System.Windows.Application.Resources%2A>允许您支持应用程序范围的主题，其中每个主题封装由单个资源字典。</span><span class="sxs-lookup"><span data-stu-id="1f89d-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="1f89d-112">下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="1f89d-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="1f89d-113">下面的示例演示如何公开的资源字典中获取应用程序范围的资源<xref:System.Windows.Application.Resources%2A>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="1f89d-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="1f89d-114">以下内容显示如何也能获取代码中的资源。</span><span class="sxs-lookup"><span data-stu-id="1f89d-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="1f89d-115">使用时要注意两点<xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="1f89d-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="1f89d-116">首先，字典*密钥*是一个对象，因此你必须使用完全相同的对象实例时设置和获取属性值。</span><span class="sxs-lookup"><span data-stu-id="1f89d-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="1f89d-117">（请注意，使用字符串时键区分大小写。）其次，字典*值*是一个对象，因此你将需要获取的属性值时，将的值转换为所需的类型。</span><span class="sxs-lookup"><span data-stu-id="1f89d-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f89d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f89d-118">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [<span data-ttu-id="1f89d-119">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="1f89d-119">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="1f89d-120">合并资源字典</span><span class="sxs-lookup"><span data-stu-id="1f89d-120">Merged Resource Dictionaries</span></span>](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)
