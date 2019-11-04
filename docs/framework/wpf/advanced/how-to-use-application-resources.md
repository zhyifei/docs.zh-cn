---
title: 如何：使用应用程序资源
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF]
- resources [WPF], application resources
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
ms.openlocfilehash: e4114466fa8016f8e31100d7a37038b0abfdccca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460266"
---
# <a name="how-to-use-application-resources"></a>如何：使用应用程序资源
本示例演示如何使用应用程序资源。  
  
## <a name="example"></a>示例  
 以下示例演示应用程序定义文件。 应用程序定义文件定义资源部分（<xref:System.Windows.Application.Resources%2A> 属性的值）。 构成应用程序的所有其他页均可访问在应用程序级别定义的资源。 这种情况下，资源是声明样式。 由于包含控件模板的完整样式可能会很长，因此此示例将省略在样式的 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 属性 setter 中定义的控件模板。  
  
 [!code-xaml[ResourcesApplication#PreTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xaml[ResourcesApplication#PostTemplateResource](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 下面的示例演示了一个 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 页，该页面引用上一个示例定义的应用程序级资源。 使用指定所请求资源的唯一资源键的[StaticResource 标记扩展](staticresource-markup-extension.md)来引用资源。 在当前页中没有找到具有“GelButton”键的资源，所以请求资源的资源查找范围超出当前页，进入已定义的应用程序级资源。  
  
 [!code-xaml[ResourcesApplication#ConsumingPage](~/samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## <a name="see-also"></a>请参阅

- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [应用程序管理概述](../app-development/application-management-overview.md)
- [帮助主题](resources-how-to-topics.md)
