---
title: x:Arguments 指令
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 338286b417c78b7cceeb30188e888928a15607cd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458650"
---
# <a name="xarguments-directive"></a>x:Arguments 指令
为 XAML 中的非参数构造函数对象元素声明或工厂方法对象声明包构造参数。  
  
## <a name="xaml-element-usage-nonparameterless-constructor"></a>XAML 元素使用情况（Nonparameterless 构造函数）  
  
```xaml  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>XAML 元素使用情况（工厂方法）  
  
```xaml  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|一个或多个对象元素，用于指定要传递给支持的非参数构造函数或工厂方法的参数。<br /><br /> 典型用法是使用对象元素中的初始化文本来指定实际参数值。 请参阅示例部分。<br /><br /> 元素的顺序非常重要。 按顺序排列的 XAML 类型必须与后备构造函数或工厂方法重载的类型和类型顺序相匹配。|  
|`methodName`|应处理任意 `x:Arguments` 参数的工厂方法的名称。|  
  
## <a name="dependencies"></a>依赖项  
 `x:FactoryMethod` 可以修改 `x:Arguments` 适用的范围和行为。  
  
 如果未指定 `x:FactoryMethod`，`x:Arguments` 适用于后备构造函数的备用（非默认）签名。  
  
 如果指定 `x:FactoryMethod`，`x:Arguments` 适用于命名方法的重载。  
  
## <a name="remarks"></a>备注  
 XAML 2006 可以通过初始化文本支持非默认初始化。 但是，初始化文本构造技术的实际应用程序是有限的。 初始化文本被视为单个文本字符串;因此，它仅添加单个参数初始化的功能，除非为构造行为定义了一个类型转换器，此构造行为可分析自定义信息项和字符串中的自定义分隔符。 此外，文本字符串到对象逻辑可能是给定的 XAML 分析器用于处理除 true 字符串以外的基元的本机默认类型转换器。  
  
 由于指令标记不引用包含对象元素的类型，因此 `x:Arguments` XAML 用法不是属性元素的用法。 它更类似于其他指令，如 `x:Code`，其中，元素 demarks 的范围应将标记解释为子内容的默认值以外的其他指令。 在这种情况下，每个对象元素的 XAML 类型会传达有关参数类型的信息，XAML 分析器使用这些参数类型来确定 `x:Arguments` 用量尝试引用哪个特定构造函数工厂方法签名。  
  
 正在构造的对象元素的 `x:Arguments` 必须位于对象元素的任何其他属性元素、内容、内部文本或初始化字符串之前。 `x:Arguments` 中的对象元素可以包括属性和初始化字符串，如该 XAML 类型及其后备构造函数或工厂方法所允许的一样。 对于对象或参数，可以通过引用已建立的前缀映射来指定默认 XAML 命名空间之外的自定义 XAML 类型或 XAML 类型。  
  
 XAML 处理器使用以下准则来确定应如何使用 `x:Arguments` 中指定的参数来构造对象。 如果指定 `x:FactoryMethod`，则会将信息与指定的 `x:FactoryMethod` 进行比较（请注意，`x:FactoryMethod` 的值是方法名称，并且命名方法可以具有重载。 如果未指定 `x:FactoryMethod`，则会将信息与对象的所有公共构造函数重载集进行比较。 然后，XAML 处理逻辑会比较参数的数目，并选择具有匹配 arity 的重载。 如果有多个匹配项，则 XAML 处理器应根据提供的对象元素的 XAML 类型来比较参数的类型。 如果仍有多个匹配项，则 XAML 处理器行为是不确定的。 如果指定了 `x:FactoryMethod` 但该方法无法解析，则 XAML 处理器应引发异常。  
  
 从技术上讲，可以 `<x:Arguments>string</x:Arguments>` XAML 属性用法。 但是，这不会提供除通过初始化文本和类型转换器以外的任何功能，并且使用此语法不是 XAML 2009 工厂方法功能的设计意图。  
  
## <a name="examples"></a>示例  
 下面的示例演示一个无参数的构造函数签名，然后是访问该签名 `x:Arguments` 的 XAML 用法。  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 下面的示例演示了一个目标工厂方法签名，然后是访问该签名 `x:Arguments` 的 XAML 用法。  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a>请参阅

- [定义与 .NET Framework XAML 服务一起使用的自定义类型](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [XAML 概述 (WPF)](../../desktop-wpf/fundamentals/xaml.md)
