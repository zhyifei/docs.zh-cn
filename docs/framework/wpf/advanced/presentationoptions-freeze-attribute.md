---
title: PresentationOptions:Freeze 特性
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991430"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze 特性
将包含`true` <xref:System.Windows.Freezable.IsFrozen%2A> 元素的<xref:System.Windows.Freezable>状态设置为。 如果<xref:System.Windows.Freezable>未指定属性<xref:System.Windows.Freezable.IsFrozen%2A>，则的默认行为<xref:System.Windows.Freezable> 是在加载时，并且依赖于运行时的常规行为。`false` `PresentationOptions:Freeze`  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`PresentationOptions`|XML 命名空间前缀，可以是每个 XML 1.0 规范的任何有效的前缀字符串。 在本`PresentationOptions`文档中，前缀用于标识目的。|  
|`freezableElement`|一个实例化的任何派生类的<xref:System.Windows.Freezable>元素。|  
  
## <a name="remarks"></a>备注  
 `Freeze`特性是`http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`在 XML 命名空间中定义的唯一特性或其他编程元素。 此特殊命名空间中存在 `Freeze` 属性，因此可将其指定为可忽略，并使用[mc：可忽略属性](mc-ignorable-attribute.md)作为根元素声明的一部分。 `Freeze`必须能够被忽略的原因是，并非所有[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现<xref:System.Windows.Freezable>都能够在加载时冻结[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ; 此功能不是规范的组成部分。  
  
 处理`Freeze`属性的功能专门内置[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]于处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]已编译应用程序的处理器。 任何类都不支持该特性，且特性语法不可扩展或可修改。 如果要实现[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]自己的处理器，可以选择在加载时并行处理元素上<xref:System.Windows.Freezable>的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `Freeze`属性时，并行处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器的冻结行为。  
  
 `Freeze` 除`true` （不区分大小写）以外的其他属性值将生成加载时错误。 （将`Freeze`属性指定为`false`不是错误，但这已是默认值，因此，将设置`false`为不执行任何操作）。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Freezable>
- [Freezable 对象概述](freezable-objects-overview.md)
- [mc:Ignorable 特性](mc-ignorable-attribute.md)
