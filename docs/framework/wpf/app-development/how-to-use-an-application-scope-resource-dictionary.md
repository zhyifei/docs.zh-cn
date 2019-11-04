---
title: 如何：使用应用程序范围的资源字典
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459795"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a><span data-ttu-id="f785f-102">如何：使用应用程序范围的资源字典</span><span class="sxs-lookup"><span data-stu-id="f785f-102">How to: Use an Application-Scope Resource Dictionary</span></span>
<span data-ttu-id="f785f-103">本示例显示如何定义和使用应用程序范围的自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="f785f-103">This example shows how to define and use an application-scope custom resource dictionary.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f785f-104">示例</span><span class="sxs-lookup"><span data-stu-id="f785f-104">Example</span></span>  
 <span data-ttu-id="f785f-105"><xref:System.Windows.Application> 公开共享资源的应用程序范围存储： <xref:System.Windows.Application.Resources%2A>。</span><span class="sxs-lookup"><span data-stu-id="f785f-105"><xref:System.Windows.Application> exposes an application-scope store for shared resources: <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="f785f-106">默认情况下，使用 <xref:System.Windows.ResourceDictionary> 类型的实例初始化 <xref:System.Windows.Application.Resources%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="f785f-106">By default, the <xref:System.Windows.Application.Resources%2A> property is initialized with an instance of the <xref:System.Windows.ResourceDictionary> type.</span></span> <span data-ttu-id="f785f-107">使用 <xref:System.Windows.Application.Resources%2A>获取和设置应用程序范围的属性时，可以使用此实例。</span><span class="sxs-lookup"><span data-stu-id="f785f-107">You use this instance when you get and set application-scope properties using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="f785f-108">有关详细信息，请参阅[如何：获取和设置应用程序范围资源](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="f785f-108">For more information, see [How to: Get and Set an Application-Scope Resource](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).</span></span>
  
 <span data-ttu-id="f785f-109">如果有多个使用 <xref:System.Windows.Application.Resources%2A>设置的资源，则可以改为使用自定义资源字典来存储这些资源并将 <xref:System.Windows.Application.Resources%2A> 设置为。</span><span class="sxs-lookup"><span data-stu-id="f785f-109">If you have multiple resources that you set using <xref:System.Windows.Application.Resources%2A>, you can instead use a custom resource dictionary to store those resources and set <xref:System.Windows.Application.Resources%2A> with it instead.</span></span> <span data-ttu-id="f785f-110">下面演示了如何使用 XAML 声明自定义资源字典。</span><span class="sxs-lookup"><span data-stu-id="f785f-110">The following shows how you declare a custom resource dictionary using XAML.</span></span>
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 <span data-ttu-id="f785f-111">使用 <xref:System.Windows.Application.Resources%2A> 交换整个资源字典允许您支持应用程序范围的主题，其中每个主题都由单个资源字典封装。</span><span class="sxs-lookup"><span data-stu-id="f785f-111">Swapping entire resource dictionaries using <xref:System.Windows.Application.Resources%2A> allows you to support application-scope themes, where each theme is encapsulated by a single resource dictionary.</span></span> <span data-ttu-id="f785f-112">下面的示例演示如何设置 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="f785f-112">The following example shows how to set the <xref:System.Windows.ResourceDictionary>.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 <span data-ttu-id="f785f-113">下面演示了如何从 XAML 中 <xref:System.Windows.Application.Resources%2A> 公开的资源字典中获取应用程序范围的资源。</span><span class="sxs-lookup"><span data-stu-id="f785f-113">The following shows how you can get application-scope resources from the resource dictionary exposed by <xref:System.Windows.Application.Resources%2A> in XAML.</span></span>  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 <span data-ttu-id="f785f-114">以下内容显示如何也能获取代码中的资源。</span><span class="sxs-lookup"><span data-stu-id="f785f-114">The following shows how you can also get the resources in code.</span></span>  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 <span data-ttu-id="f785f-115">使用 <xref:System.Windows.Application.Resources%2A>时有两个注意事项。</span><span class="sxs-lookup"><span data-stu-id="f785f-115">There are two considerations to make when using <xref:System.Windows.Application.Resources%2A>.</span></span> <span data-ttu-id="f785f-116">首先，字典*键*是一个对象，因此在设置和获取属性值时，必须使用完全相同的对象实例。</span><span class="sxs-lookup"><span data-stu-id="f785f-116">First, the dictionary *key* is an object, so you must use exactly the same object instance when both setting and getting a property value.</span></span> <span data-ttu-id="f785f-117">（请注意，使用字符串时，该键区分大小写。）其次，字典*值*是一个对象，因此在获取属性值时，必须将该值转换为所需的类型。</span><span class="sxs-lookup"><span data-stu-id="f785f-117">(Note that the key is case-sensitive when using a string.) Second, the dictionary *value* is an object, so you will have to convert the value to the desired type when getting a property value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f785f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f785f-118">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [<span data-ttu-id="f785f-119">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="f785f-119">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="f785f-120">合并资源字典</span><span class="sxs-lookup"><span data-stu-id="f785f-120">Merged Resource Dictionaries</span></span>](../advanced/merged-resource-dictionaries.md)
