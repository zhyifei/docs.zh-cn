---
title: 如何：使用可本地化的应用程序中的资源
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: ad257e7703bcee8f71da78ad5928d7999365c38f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376152"
---
# <a name="how-to-use-resources-in-localizable-applications"></a><span data-ttu-id="59f32-102">如何：使用可本地化的应用程序中的资源</span><span class="sxs-lookup"><span data-stu-id="59f32-102">How to: Use Resources in Localizable Applications</span></span>
<span data-ttu-id="59f32-103">本地化是指以适应[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]不同的区域性。</span><span class="sxs-lookup"><span data-stu-id="59f32-103">Localization means to adapt a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to different cultures.</span></span> <span data-ttu-id="59f32-104">为此，必须翻译诸如标题、描述、列表框项等文本。</span><span class="sxs-lookup"><span data-stu-id="59f32-104">To do this, text such as titles, captions, list box items and so forth have to be translated.</span></span> <span data-ttu-id="59f32-105">为简化翻译过程，要翻译的项需收集到资源文件中。</span><span class="sxs-lookup"><span data-stu-id="59f32-105">To make translation easier the items to be translated are collected into resource files.</span></span> <span data-ttu-id="59f32-106">请参阅[本地化应用程序](how-to-localize-an-application.md)有关如何创建本地化的资源文件的信息。</span><span class="sxs-lookup"><span data-stu-id="59f32-106">See [Localize an Application](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="59f32-107">若要使[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序可本地化，开发人员需要生成一个资源程序集的所有可本地化的资源。</span><span class="sxs-lookup"><span data-stu-id="59f32-107">To make a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="59f32-108">资源程序集本地化为不同语言和代码隐藏功能使用资源管理[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]加载。</span><span class="sxs-lookup"><span data-stu-id="59f32-108">The resource assembly is localized into different languages, and the code-behind uses resource management [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] to load.</span></span> <span data-ttu-id="59f32-109">所需的文件之一[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序是项目文件 (.proj)。</span><span class="sxs-lookup"><span data-stu-id="59f32-109">One of the files required for a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application is a project file (.proj).</span></span> <span data-ttu-id="59f32-110">应用程序中使用的所有资源都应包括在项目文件中。</span><span class="sxs-lookup"><span data-stu-id="59f32-110">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="59f32-111">下面的代码示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="59f32-111">The following code example shows this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59f32-112">示例</span><span class="sxs-lookup"><span data-stu-id="59f32-112">Example</span></span>  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 <span data-ttu-id="59f32-113">若要在应用程序中使用资源，实例化<xref:System.Resources.ResourceManager>并加载你想要使用的资源。</span><span class="sxs-lookup"><span data-stu-id="59f32-113">To use a resource in your application, you instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="59f32-114">下面的示例演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="59f32-114">The following demonstrates how to do this.</span></span>  
  
 [!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
