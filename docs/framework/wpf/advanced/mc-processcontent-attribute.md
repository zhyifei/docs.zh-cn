---
title: "mc:ProcessContent 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aaf83fe66d5367d5e51428cb8f35aa88c12c9c39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="mcprocesscontent-attribute"></a>mc:ProcessContent 特性
指定哪些[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]元素仍应具有处理相关的父元素的内容，即使可能忽略的直接父元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]由于指定的处理器[mc： 可忽略属性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md). `mc:ProcessContent`属性支持标记兼容性，为自定义命名空间映射和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]版本控制。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*ignorablePrefix*|根据 XML 1.0 规范任何有效的前缀字符串。|  
|*ignorableUri*|任何有效的 URI，指定命名空间中的，根据 XML 1.0 规范。|  
|*ThisElementCanBeIgnored*|可通过忽略的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现，如果基础类型不能解析。|  
|*[内容]*|*ThisElementCanBeIgnored*标记可忽略。 如果处理器忽略该元素， *[内容]*由处理*对象*。|  
  
## <a name="remarks"></a>备注  
 默认情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略中被忽略的元素的内容。 你可以指定的特定元素由`mc:ProcessContent`，和一个[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将继续处理中被忽略的元素的内容。 此值通常会在内容嵌套在多个标记，至少一个可以忽略，至少一个不是可忽略使用。  
  
 在属性中，例如使用空间分隔符，可指定多个前缀： `mc:ProcessContent="ignore:Element1 ignore:Element2"`。  
  
 [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]命名空间定义其他元素和属性未记录的此区域内[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]。 有关详细信息，请参阅[XML 标记兼容性规范](http://go.microsoft.com/fwlink/?LinkId=73824)。  
  
## <a name="see-also"></a>另请参阅  
 [mc:Ignorable 特性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
