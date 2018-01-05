---
title: "x:FactoryMethod 指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58349c5440d0062c64346933e48b64de6c4c7b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xfactorymethod-directive"></a>x:FactoryMethod 指令
指定 XAML 处理器应使用解决其后备类型后初始化对象构造函数以外的方法。  
  
## <a name="xaml-attribute-usage-no-xarguments"></a>XAML 属性用法，没有 x： 自变量  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a>XAML 属性用法，作为元素的 x： 自变量  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`methodname`|XAML 处理器调用以初始化为指定的实例方法的字符串方法名称`object`。 请参阅“备注”。|  
|`oneOrMoreObjectElements`|指定工厂方法参数的对象的一个或多个对象元素。 顺序很重要;它表示应在其中到工厂方法中传递自变量的顺序。|  
  
## <a name="remarks"></a>备注  
 如果`methodname`是实例方法，它不能限定。  
  
 支持为工厂方法的静态方法。 如果`methodname`是静态方法，`methodname`作为提供*typeName*。*methodName*组合，其中*typeName*命名定义的静态工厂方法的类。 *typeName*可以由前缀限定如果指向映射 xmlns 中的类型。 *typeName*可以与不同的类型`typeof(``object``)`。  
  
 工厂方法必须是类型的支持相关对象元素的声明的公共方法。  
  
 工厂方法必须返回可分配给相关对象的实例。 工厂方法应永远不会返回 null。  
  
 `x:Arguments`工厂方法签名的最佳匹配项的原则进行操作。 首先，匹配计算的参数计数。 如果没有为参数计数的多个可能的匹配项，参数类型为则确定计算和最佳匹配。 如果没有仍不明确性评估此阶段完成之后，XAML 处理器行为不确定。  
  
 `x:FactoryMethod`元素用法不是属性元素用法在典型的意义上，因为指令标记不引用包含对象元素的类型。 它预计该元素的用法是不如特性用法不太常见。 `x:Arguments`（属性或元素使用） 可用于沿`x:FactoryMethod`元素用法，但这是不专门部分中所示使用情况。  
  
 `x:FactoryMethod`如元素必须位于任何其他属性元素之前，必须位于任何之前`x:Arguments`还提供作为元素，以及必须前面的任何内容/内部文本/初始化文本。  
  
## <a name="see-also"></a>请参阅  
 [x:Arguments 指令](../../../docs/framework/xaml-services/x-arguments-directive.md)
