---
title: 类、结构和接口的名称
ms.date: 03/30/2017
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576137"
---
# <a name="names-of-classes-structs-and-interfaces"></a>类、结构和接口的名称
以下命名准则适用于常规类型命名。  
  
 **✓ 要**使用 PascalCasing，用名词或名词短语命名类和结构。
  
 这将类型名称与使用动词短语命名的方法区分开来。
  
 **✓ 要**使用形容词短语命名接口，或偶尔用名词或名词短语命名接口。
  
 应该很少使用名词和名词短语，它们可能表明类型应该是抽象类，而不是接口。
  
 **X 不要**给类名加前缀（例如，“C”）。
  
 **✓ 考虑**使用基类的名称结束派生类的名称。
  
 这样非常易读，并且清楚地解释了这种关系。 这是代码中的一些示例，包括： `ArgumentOutOfRangeException`，这是一种`Exception`类型，和`SerializableAttribute`，这是一种`Attribute`类型。 但是，在应用本准则时使用合理的判断非常重要;例如，`Button`类是一种`Control`类型，尽管`Control`未出现在其名称中。  
  
 **✓ 要**在接口名称前加上字母I，以表示该类型是接口。
  
 例如， `IComponent` （描述性名词）， `ICustomAttributeProvider` （名词短语），和`IPersistable`（形容词） 是适当的接口名称。 与其他类型名称一样，避免使用缩写。  
  
 **✓ 要**确保当您定义类和接口对时，类名称和接口名称仅由“I”前缀不同，其中类是接口的标准实现。  
  
## <a name="names-of-generic-type-parameters"></a>泛型类型参数的名称  
 泛型被添加到 .NET Framework 2.0中。 该功能引入了一种称为*类型参数*的新标识符。
  
 **✓ 要**使用描述性名称命名泛型类型参数，除非单字母名称完全不言自明且描述性名称并没有太多意义。
  
 **✓ 考虑**使用`T`作为具有一个单字母类型参数的类型的类型参数名称。  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ 要**用`T`作为描述性类型参数名称的前缀。  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ 考虑**指示对参数名称中的类型参数施加约束。  
  
 例如，将参数约束为`ISession`可能称为`TSession`。  
  
## <a name="names-of-common-types"></a>常见类型的名称  
 **✓ 要**在命名从某些.NET Framework类型派生或实现某些.NET Framework类型的类型时，请遵循下表中描述的准则。
  
|基类型|派生/实现类型准则|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ 要**在自定义属性类的名称中添加后缀"Attribute"。|  
|`System.Delegate`|**✓ 要**在事件中使用的委托的名称中添加后缀"EventHandler"。<br /><br /> **✓ 要**在除用作事件处理程序之外的委托名称中添加后缀“Callback”。<br /><br /> **X 不要**将后缀"Delegate"添加到委托。|  
|`System.EventArgs`|**✓ 要**添加后缀"EventArgs。"|  
|`System.Enum`|**X 不要**从此类派生; 使用支持你的语言的关键字; 例如，在 C# 中，使用`enum`关键字。<br /><br /> **X 不要**添加后缀"Enum"或"Flag"。|  
|`System.Exception`|**✓ 要**添加后缀"Exception"。|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ 要**添加后缀"Dictionary"。 请注意，`IDictionary`是一种特定类型的集合，但这一准则将优先于后面的更多常规集合准则。|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ 要**添加后缀"Collection"。|  
|`System.IO.Stream`|**✓ 要**添加后缀"Stream"。|  
|`CodeAccessPermission IPermission`|**✓ 要**添加后缀"Permission"。|  
  
## <a name="naming-enumerations"></a>命名枚举  
 一般情况下，枚举类型（也称为枚举）的名称通常应遵循标准的类型命名规则（PascalCasing等）。 但是，还有专门适用于枚举的其他准则。  
  
 **✓ 要**使用单数形式的类型名称进行枚举，除非它的值是位字段。  
  
 **✓ 要**使用复数形式的类型名称作为值为位字段的枚举，也称为标志枚举。  
  
 **X 不要**在枚举类型名称中使用"Enum"后缀。  
  
 **X 不要**在枚举类型名称中使用"Flag"或"Flags"后缀。  
  
 **X 不要**在枚举值名称上使用前缀 (例如，ADO 枚举的“ad”，富文本枚举的"rtf"等。) 。 
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
