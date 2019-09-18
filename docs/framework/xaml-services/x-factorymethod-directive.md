---
title: x:FactoryMethod 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 586965dd4094e81fd830a09b64604cf33f195630
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053780"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 指令
指定一个方法，该方法不是 XAML 处理器在解析其支持类型后用于初始化对象的构造函数。  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 特性用法，无 x:Arguments  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 特性用法，x:Arguments 作为元素  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`methodname`|XAML 处理器调用以初始化指定为`object`的实例的方法的字符串方法名称。 请参阅“备注”。|  
|`oneOrMoreObjectElements`|用于指定工厂方法参数的对象的一个或多个对象元素。 顺序非常重要;它表示应将参数传递给工厂方法的顺序。|  
  
## <a name="remarks"></a>备注  
 如果`methodname`是实例方法，则不能对其进行限定。  
  
 支持静态方法作为工厂方法。 如果`methodname`是静态方法， `methodname`则以*typeName*形式提供。*方法*名称组合，其中*typeName*命名定义静态工厂方法的类。 如果引用映射的 xmlns 中的类型，则类型*名称*可以由前缀限定。 *typeName*可以是不同于`typeof(object)`的类型。  
  
 工厂方法必须是该类型的声明的公共方法，该方法支持相关的对象元素。  
  
 工厂方法必须返回可分配给相关对象的实例。 工厂方法绝不应返回 null。  
  
 `x:Arguments`对工厂方法签名的最佳匹配原则进行操作。 匹配首先计算参数计数。 如果某个参数计数有多个可能的匹配项，则将计算参数类型并确定最佳匹配项。 如果在此计算阶段后仍然存在歧义，则 XAML 处理器行为是不确定的。  
  
 由于指令标记不引用包含对象元素的类型，因此元素用法不是属性元素的用法。`x:FactoryMethod` 预期元素用法不如属性用法常见。 `x:Arguments`（特性或元素使用情况）可与`x:FactoryMethod`元素使用一起使用，但不会在用法部分专门显示。  
  
 `x:FactoryMethod`作为元素必须位于任何其他属性元素之前，必须在提供`x:Arguments`的任何元素前面作为元素，并且必须位于任何内容/内部文本/初始化文本之前。  
  
## <a name="see-also"></a>请参阅

- [x:Arguments 指令](x-arguments-directive.md)
