---
title: "如何：为依赖项属性添加所有者类型"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b93934c8f84a7257445b530e27896342bdd73aea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>如何：为依赖项属性添加所有者类型
此示例演示如何作为为不同类型注册依赖属性所有者添加类。 通过执行此操作，请[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器和属性系统都能够识别类作为其他所有者的属性。 （可选） 添加作为所有者可以选择添加类以提供特定类型的元数据。  
  
 在下面的示例中，`StateProperty`属性由就注册`MyStateControl`类。 类`UnrelatedStateControl`其自身添加的所有者为`StateProperty`使用<xref:System.Windows.DependencyProperty.AddOwner%2A>专门使用的签名，以便新的依赖项属性的元数据，因为它存在于添加类型的方法。 请注意，应提供[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]类似于示例中所示的属性的访问器[实现一个依赖项属性](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md)示例中，以及重新公开要添加的类上的依赖项属性标识符作为所有者。  
  
 如果没有包装器，依赖项属性将仍正常工作的以编程方式访问使用角度<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>。 但你通常想要使用此属性系统的行为的并行[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]属性包装器。 此包装器更加轻松地设置依赖项属性以编程方式，并使其可以设置属性为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。  
  
 若要了解如何重写默认元数据，请参阅[重写依赖项属性的元数据](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>请参阅  
 [自定义依赖属性](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
