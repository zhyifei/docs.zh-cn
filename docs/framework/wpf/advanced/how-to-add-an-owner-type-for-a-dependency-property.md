---
title: 如何：添加依赖属性的所有者类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
ms.openlocfilehash: 5ddc85d159b4bf81751428c13c234c5e53be8ad4
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401130"
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a>如何：添加依赖属性的所有者类型
此示例演示如何将类添加为为不同类型注册的依赖项属性的所有者。 通过执行此操作, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器和属性系统都能将该类识别为属性的其他所有者。 添加为所有者可以选择允许添加类提供特定于类型的元数据。  
  
 在下面的示例中`StateProperty` , 是`MyStateControl`由类注册的属性。 类`UnrelatedStateControl` `StateProperty`使用方法<xref:System.Windows.DependencyProperty.AddOwner%2A>将自身添加为的所有者, 特别是使用签名, 该签名允许依赖项属性的新元数据, 因为它存在于添加类型中。 请注意, 应为属性提供公共语言运行时 (CLR) 访问器, 与[实现依赖项属性](how-to-implement-a-dependency-property.md)示例中所示的示例类似, 并重新公开作为所有者添加的类的依赖项属性标识符。  
  
 如果不使用包装, 依赖属性仍将从使用<xref:System.Windows.DependencyObject.GetValue%2A>或<xref:System.Windows.DependencyObject.SetValue%2A>的编程访问角度来处理。 但是, 您通常需要将此属性系统行为与 CLR 属性包装器进行并行处理。 利用这些包装, 可以以编程方式轻松设置依赖属性, 并可以将属性设置为[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]属性。  
  
 若要了解如何重写默认元数据, 请参阅[重写依赖属性的元数据](how-to-override-metadata-for-a-dependency-property.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a>请参阅

- [自定义依赖属性](custom-dependency-properties.md)
- [依赖项属性概述](dependency-properties-overview.md)
