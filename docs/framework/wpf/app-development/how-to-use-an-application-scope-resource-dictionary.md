---
title: 如何：使用应用程序范围资源字典
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 589e28b3c05496e3fc17055b98240e389faed068
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007482"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="98008-102">如何：使用应用程序范围资源字典</span><span class="sxs-lookup"><span data-stu-id="98008-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="98008-103">本示例显示如何定义和使用应用程序范围的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="98008-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98008-104">示例</span><span class="sxs-lookup"><span data-stu-id="98008-104">Example</span></span>  
 <span data-ttu-id="98008-105"><xref:System.Windows.Application> 公开共享资源的应用程序作用域存储： <xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="98008-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="98008-106">默认情况下<xref:System.Windows.Application.Resources%2A>属性使用的实例初始化<xref:System.Windows.ResourceDictionary>类型。</span><span class="sxs-lookup"><span data-stu-id="98008-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="98008-107">可以使用此实例时获取和设置应用程序作用域属性使用<xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="98008-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="98008-108">有关详细信息，请参阅[如何：获取和设置应用程序范围资源](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="98008-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="98008-109">如果必须使用设置的多个资源<xref:System.Windows.Application.Resources%2A>，而是可以使用自定义资源字典来存储这些资源和设置<xref:System.Windows.Application.Resources%2A>与之相反。</span><span class="sxs-lookup"><span data-stu-id="98008-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="98008-110">下面演示如何声明使用 XAML 的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="98008-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="98008-111">交换使用整个资源字典<xref:System.Windows.Application.Resources%2A>使您能够支持应用程序范围的主题，其中每个主题封装由单个资源字典。</span><span class="sxs-lookup"><span data-stu-id="98008-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="98008-112">下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="98008-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="98008-113">下面演示了如何从通过公开的资源字典获取应用程序范围资源<xref:System.Windows.Application.Resources%2A>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="98008-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="98008-114">以下内容显示如何也能获取代码中的资源。</span><span class="sxs-lookup"><span data-stu-id="98008-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="98008-115">有两个注意事项，以便使用<xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="98008-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="98008-116">首先，字典*密钥*是一个对象，因此必须使用完全相同的对象实例时设置和获取属性值。</span><span class="sxs-lookup"><span data-stu-id="98008-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="98008-117">（请注意，使用字符串时键区分大小写。）其次，字典*值*是一个对象，因此必须将值转换为所需的类型，获取属性值时。</span><span class="sxs-lookup"><span data-stu-id="98008-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98008-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="98008-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="98008-119">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="98008-119">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="98008-120">合并资源字典</span><span class="sxs-lookup"><span data-stu-id="98008-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
