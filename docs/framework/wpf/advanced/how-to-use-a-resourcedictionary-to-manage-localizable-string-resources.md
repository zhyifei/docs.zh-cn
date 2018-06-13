---
title: 如何：使用 ResourceDictionary 来管理可本地化的字符串资源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 76ff3f688b5d3e7122254990076edb21fe6ae119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544493"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="c58d6-102">如何：使用 ResourceDictionary 来管理可本地化的字符串资源</span><span class="sxs-lookup"><span data-stu-id="c58d6-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="c58d6-103">此示例演示如何使用<xref:System.Windows.ResourceDictionary>到 Windows Presentation Foundation (WPF) 应用程序的包可本地化的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="c58d6-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="c58d6-104">使用 ResourceDictionary 来管理可本地化的字符串资源</span><span class="sxs-lookup"><span data-stu-id="c58d6-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="c58d6-105">创建<xref:System.Windows.ResourceDictionary>，其中包含你想要本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="c58d6-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="c58d6-106">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="c58d6-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="c58d6-107">此代码定义字符串资源， `localizedMessage`，类型的<xref:System.String>，从<xref:System>mscorlib.dll 中的命名空间。</span><span class="sxs-lookup"><span data-stu-id="c58d6-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="c58d6-108">添加<xref:System.Windows.ResourceDictionary>到你的应用程序，使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="c58d6-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="c58d6-109">使用字符串资源标记，使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]类似于以下。</span><span class="sxs-lookup"><span data-stu-id="c58d6-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="c58d6-110">通过如下所示的代码来使用代码隐藏文件中的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="c58d6-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="c58d6-111">对应用程序进行本地化。</span><span class="sxs-lookup"><span data-stu-id="c58d6-111">Localize the application.</span></span> <span data-ttu-id="c58d6-112">有关详细信息，请参阅[本地化应用程序](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c58d6-112">For more information, see [Localize an Application](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md).</span></span>
