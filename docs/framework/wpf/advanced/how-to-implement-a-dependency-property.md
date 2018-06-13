---
title: 如何：实现依赖属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: b0c5b33d841f43249f9559bd31f1ef8fe66ff05e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544643"
---
# <a name="how-to-implement-a-dependency-property"></a>如何：实现依赖属性
此示例演示如何备份[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]具有属性<xref:System.Windows.DependencyProperty>字段，从而定义依赖项属性。 定义自己的属性并需要其支持 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 功能的诸多方面（包括样式、数据绑定、继承、动画和默认值）时，应将其作为依赖属性实现。  
  
## <a name="example"></a>示例  
 下面的示例首先通过调用注册依赖属性<xref:System.Windows.DependencyProperty.Register%2A>方法。 用于存储名称，并且必须特征的依赖项属性的标识符字段名称<xref:System.Windows.DependencyProperty.Name%2A>你选择的依赖项属性的一部分<xref:System.Windows.DependencyProperty.Register%2A>调用，文本的字符串追加`Property`。 例如，如果你注册具有的依赖项属性<xref:System.Windows.DependencyProperty.Name%2A>的`Location`，则必须命名为你定义的依赖项属性标识符字段`LocationProperty`。  
  
 在此示例中，依赖项属性的名称并将其[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]取值函数，则`State`; 标识符字段是`StateProperty`; 属性的类型是<xref:System.Boolean>; 和注册的依赖项属性的类型是`MyStateControl`。  
  
 如果不遵循此命名模式，则设计器可能无法正确地报告属性，而且属性系统样式应用程序的某些方面可能不会以预期的方式工作。  
  
 还可为依赖属性指定默认元数据。 此示例将 `State` 依赖属性的默认值注册为 `false`。  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 若要深入了解实现依赖属性而非仅使用私有字段支持 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 属性的原因及其实现方式，请参阅[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [依赖项属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
