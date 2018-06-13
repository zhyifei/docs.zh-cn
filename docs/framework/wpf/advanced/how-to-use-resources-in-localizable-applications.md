---
title: 如何：使用可本地化的应用程序中的资源
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 82a24feb4008b6cfd7c1751c6449c0d8515ffe87
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544698"
---
# <a name="how-to-use-resources-in-localizable-applications"></a>如何：使用可本地化的应用程序中的资源
本地化即以适应[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]到不同的区域性。 为此，必须翻译诸如标题、描述、列表框项等文本。 为简化翻译过程，要翻译的项需收集到资源文件中。 请参阅[本地化应用程序](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)有关如何创建本地化的资源文件的信息。 若要使[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序可本地化，开发人员需要将内置资源程序集的所有可本地化的资源。 资源程序集已本地化为不同的语言，并隐藏代码使用资源管理[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]加载。 所需的文件之一[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序是项目文件 (.proj)。 应用程序中使用的所有资源都应包括在项目文件中。 下面的代码示例演示了此过程。  
  
## <a name="example"></a>示例  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 若要在你的应用程序中使用的资源，实例化<xref:System.Resources.ResourceManager>并加载你想要使用的资源。 下面的示例演示如何执行此操作。  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]
