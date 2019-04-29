---
title: x:Reference 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938874"
---
# <a name="xreference-markup-extension"></a>x:Reference 标记扩展
在 XAML 标记中其他地方声明的实例的引用。 引用所引用的元素的`x:Name`。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 对象元素用法  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`instancexName`|`x:Name`值 (或值<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-标识属性) 的引用的实例。|  
  
## <a name="remarks"></a>备注  
 `x:Reference` 提供对一个元素的引用概念，否则在特定框架，如 WPF 中实现 XAML 语言级别支持。  
  
## <a name="xreference-and-wpf"></a>x： 引用和 WPF  
 在 WPF 和 XAML 2006 中，元素的引用进行寻址的框架级别功能<xref:System.Windows.Data.Binding.ElementName%2A>绑定。 对于大多数 WPF 应用程序和方案，<xref:System.Windows.Data.Binding.ElementName%2A>应仍使用绑定。 此一般指南的例外情况可能包括用例，其中没有数据上下文或使数据绑定无法实际应用其他作用域注意事项，且不涉及标记编译。  
  
 `x:Reference` 一种构造是在 XAML 2009 中定义。 在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。 标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。
