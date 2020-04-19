---
title: x:FactoryMethod 指令
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432784"
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 指令
指定 XAML 处理器应在解析对象支持类型后使用来初始化对象的构造函数以外的方法。  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 属性用法，无 x：参数  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 属性用法，x：参数作为元素  
  
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
|`methodname`|XAML 处理器调用的方法的字符串方法名称，用于初始化指定为`object`的实例。 请参阅“备注”。|  
|`oneOrMoreObjectElements`|指定工厂方法参数的对象的一个或多个对象元素。 订单很重要;它表示参数应传递给工厂方法的顺序。|  
  
## <a name="remarks"></a>备注  
 如果是`methodname`实例方法，则无法限定它。  
  
 支持作为工厂方法的静态方法。 如果是`methodname`静态方法，`methodname`则作为`typeName.methodName`组合提供，其中`typeName`命名定义静态工厂方法的类。 `typeName`如果引用映射的 xmlns 中的类型，则可以在前缀限定。 `typeName`可以是与`typeof(object)`不同的类型。  
  
 工厂方法必须是支持相关对象元素的类型声明的公共方法。  
  
 工厂方法必须返回可分配给相关对象的实例。 工厂方法绝不应返回 null。  
  
 `x:Arguments`操作的原则是最佳匹配工厂方法的签名。 匹配首先计算参数计数。 如果参数计数有多个可能的匹配项，则计算参数类型并确定最佳匹配。 如果在此评估阶段之后仍有歧义，则未定义 XAML 处理器行为。  
  
 元素`x:FactoryMethod`用法在典型意义上不是属性元素用法，因为指令标记不引用包含对象元素的类型。 预计元素使用比属性用法少。 `x:Arguments`（属性或元素用法）可以随元素使用一`x:FactoryMethod`起使用，但"使用"部分没有具体显示。  
  
 `x:FactoryMethod`作为元素必须位于任何其他属性元素之前，必须位于任何`x:Arguments`也作为元素提供的元素之前，并且必须位于任何内容/内部文本/初始化文本之前。  
  
## <a name="see-also"></a>请参阅

- [x:Arguments 指令](xarguments-directive.md)
