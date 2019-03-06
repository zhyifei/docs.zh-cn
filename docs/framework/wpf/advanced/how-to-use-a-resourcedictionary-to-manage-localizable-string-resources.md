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
ms.openlocfilehash: e28086d8c97070b854ebdea35fe347c64c5cd7ac
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377932"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="43356-102">如何：使用 ResourceDictionary 来管理可本地化的字符串资源</span><span class="sxs-lookup"><span data-stu-id="43356-102">How to: Use a ResourceDictionary to Manage Localizable String Resources</span></span>
<span data-ttu-id="43356-103">此示例演示如何使用<xref:System.Windows.ResourceDictionary>到包的 Windows Presentation Foundation (WPF) 应用程序的可本地化的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="43356-103">This example shows how to use a <xref:System.Windows.ResourceDictionary> to package localizable string resources for Windows Presentation Foundation (WPF) applications.</span></span>  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a><span data-ttu-id="43356-104">使用 ResourceDictionary 来管理可本地化的字符串资源</span><span class="sxs-lookup"><span data-stu-id="43356-104">To use a ResourceDictionary to manage localizable string resources</span></span>  
  
1.  <span data-ttu-id="43356-105">创建<xref:System.Windows.ResourceDictionary>，其中包含你想要本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="43356-105">Create a <xref:System.Windows.ResourceDictionary> that contains the strings you would like to localize.</span></span> <span data-ttu-id="43356-106">以下代码显示一个示例。</span><span class="sxs-lookup"><span data-stu-id="43356-106">The following code shows an example.</span></span>  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     <span data-ttu-id="43356-107">此代码定义的字符串资源， `localizedMessage`，类型的<xref:System.String>，从<xref:System>mscorlib.dll 中的命名空间。</span><span class="sxs-lookup"><span data-stu-id="43356-107">This code defines a string resource, `localizedMessage`, of type <xref:System.String>, from the <xref:System> namespace in mscorlib.dll.</span></span>  
  
2.  <span data-ttu-id="43356-108">添加<xref:System.Windows.ResourceDictionary>到应用程序，使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="43356-108">Add the <xref:System.Windows.ResourceDictionary> to your application, using the following code.</span></span>  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  <span data-ttu-id="43356-109">使用标记中的字符串资源使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]如下所示。</span><span class="sxs-lookup"><span data-stu-id="43356-109">Use the string resource from markup, using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] like the following.</span></span>  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  <span data-ttu-id="43356-110">通过如下所示的代码来使用代码隐藏文件中的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="43356-110">Use the string resource from code-behind, using code like the following.</span></span>  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  <span data-ttu-id="43356-111">对应用程序进行本地化。</span><span class="sxs-lookup"><span data-stu-id="43356-111">Localize the application.</span></span> <span data-ttu-id="43356-112">有关详细信息，请参阅[本地化应用程序](how-to-localize-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="43356-112">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>
