---
title: "如何：使用应用程序资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23f49481806d386bece1ad0634dd635c9eaf51f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-application-resources"></a>如何：使用应用程序资源
本示例演示如何使用应用程序资源。  
  
## <a name="example"></a>示例  
 以下示例演示应用程序定义文件。 应用程序定义文件定义的资源节 (的值<xref:System.Windows.Application.Resources%2A>属性)。 构成应用程序的所有其他页均可访问在应用程序级别定义的资源。 这种情况下，资源是声明样式。 包含控件模板的完整样式会需要较长，因为此示例中省略中定义的控件模板<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性 setter 的样式。  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 下面的示例演示[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]引用前面的示例定义该应用程序级别资源的页。 通过引用该资源[否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)，它指定请求的资源的唯一资源键。 在当前页中没有找到具有“GelButton”键的资源，所以请求资源的资源查找范围超出当前页，进入已定义的应用程序级资源。  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>另请参阅  
 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [应用程序管理概述](../../../../docs/framework/wpf/app-development/application-management-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
