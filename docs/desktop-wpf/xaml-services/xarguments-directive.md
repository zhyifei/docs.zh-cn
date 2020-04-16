---
title: x:Arguments 指令
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432832"
---
# <a name="xarguments-directive"></a>x:Arguments 指令

在 XAML 或工厂方法对象声明中为非无参数构造函数对象元素声明打包构造参数。

## <a name="xaml-element-usage-nonparameterless-constructor"></a>XAML 元素使用（无参数构造函数）

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a>XAML 元素用法（工厂方法）

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
|`oneOrMoreObjectElements`|指定要传递给支持的非无参数构造函数或工厂方法的参数的一个或多个对象元素。<br /><br /> 典型用法是使用对象元素中的初始化文本来指定实际参数值。 请参阅示例部分。<br /><br /> 元素的顺序很重要。 XAML 类型顺序必须与后备构造函数或工厂方法重载的类型和类型顺序匹配。|
|`methodName`|应处理任何`x:Arguments`参数的工厂方法的名称。|

## <a name="dependencies"></a>依赖项

`x:FactoryMethod`可以修改`x:Arguments`适用的范围和行为。

如果未`x:FactoryMethod`指定，`x:Arguments`则应用于支持构造函数的备用（非默认）签名。

如果`x:FactoryMethod`指定，`x:Arguments`则应用于命名方法的重载。

## <a name="remarks"></a>备注

XAML 2006 可通过初始化文本支持非默认初始化。 然而，初始化文本构造技术的实际应用有限。 初始化文本被视为单个文本字符串;因此，它仅添加单个参数初始化的功能，除非为构造行为定义类型转换器，该构造行为可以从字符串解析自定义信息项和自定义分隔符。 此外，到对象逻辑的文本字符串可能是给定的 XAML 解析器的本机默认类型转换器，用于处理真字符串以外的基元。

`x:Arguments` XAML 用法在典型意义上不是属性元素用法，因为指令标记不引用包含对象元素的类型。 它更类似于其他指令，例如`x:Code`元素将标记的范围解释为子内容的默认值以外的范围。 在这种情况下，每个对象元素的 XAML 类型传达有关参数类型的信息，XAML 解析器使用该类型来确定`x:Arguments`使用方法尝试引用的特定构造函数工厂方法签名。

`x:Arguments`对于正在构造的对象元素，必须位于对象元素的任何其他属性元素、内容、内部文本或初始化字符串之前。 中`x:Arguments`的对象元素可以包括属性和初始化字符串，这是 XAML 类型及其支持构造函数或工厂方法所允许的。 对于对象或参数，可以通过引用已建立的前缀映射来指定自定义 XAML 类型或 XAML 类型，这些类型在默认 XAML 命名空间之外。

XAML 处理器使用以下准则来确定如何在 中`x:Arguments`指定的参数用于构造对象。 如果`x:FactoryMethod`指定，则将信息与指定的`x:FactoryMethod`（请注意，值`x:FactoryMethod`是方法名称，并且命名方法可以具有重载。 如果未`x:FactoryMethod`指定，则将信息与对象的所有公共构造函数重载集进行比较。 然后，XAML 处理逻辑比较参数数，并选择具有匹配的参数的重载。 如果有多个匹配项，XAML 处理器应根据提供的对象元素的 XAML 类型比较参数类型。 如果仍然有多个匹配项，则未定义 XAML 处理器行为。 如果指定`x:FactoryMethod`了 ，但方法无法解决，XAML 处理器应引发异常。

从技术上讲，XAML`<x:Arguments>string</x:Arguments>`属性使用是可能的。 但是，除了通过初始化文本和类型转换器可以执行哪些功能之外，这没有任何功能，使用此语法不是 XAML 2009 工厂方法功能的设计意图。

## <a name="examples"></a>示例

下面的示例显示一个非无参数构造函数签名，然后是该签名的`x:Arguments`XAML 用法。

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

下面的示例显示目标工厂方法签名，然后显示该签名的`x:Arguments`XAML 用法。

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

- [定义与 .NET XAML 服务一起使用的自定义类型](define-custom-types.md)
- [XAML 概述 (WPF)](../fundamentals/xaml.md)
