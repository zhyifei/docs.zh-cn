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
  
 **✓ 务必**通过使用 PascalCasing，用名词或名词短语命名类和结构。  
  
 这将类型名称与使用谓词短语命名的方法区分开来。  
  
 **✓ 务必**使用形容词短语命名接口，或偶尔用名词或名词短语命名接口。  
  
 应少使用名词和名词短语，它们可能会指示类型为抽象类而非接口。  
  
 **X DO NOT** 为前缀 (例如，"C") 的类名。  
  
 **✓ CONSIDER** 结束的名称派生类同名的基类。  
  
 这是非常可读，并且清楚地说明关系。 这在代码中的一些示例包括： `ArgumentOutOfRangeException`，这是一种类型的`Exception`，和`SerializableAttribute`，这是一种类型的`Attribute`。 但是，务必使用合理的判断，在将应用此原则;例如，`Button`类是一种类型的`Control`事件，尽管`Control`未出现在其名称。  
  
 **✓ DO** 前缀接口名称以字母 I，以指示类型是接口。  
  
 例如， `IComponent` （描述性名词）， `ICustomAttributeProvider` （名词短语），和`IPersistable`（形容词） 是适当的接口名称。 与其他类型名称，避免缩写。  
  
 **✓ DO** 确保的名称不同仅通过"I"前缀的接口名称定义其中类是接口的标准实现的类 – 接口对时。  
  
## <a name="names-of-generic-type-parameters"></a>泛型类型参数的名称  
 泛型已添加到.NET Framework 2.0。 推出的功能的一种新的标识符称为*类型参数*。  
  
 **✓ DO** 使用描述性名称 name 泛型类型参数，除非单个字母的名称是完全一目了然，并且描述性的名称将不会增加价值。  
  
 **✓ CONSIDER** 使用`T`作为具有一个单字母类型参数的类型的类型参数名称。  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ DO** 前缀描述性类型参数名的`T`。  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ CONSIDER** ，该值指示约束放置在类型参数在参数名。  
  
 例如，将参数约束为`ISession`可能调用`TSession`。  
  
## <a name="names-of-common-types"></a>常见类型的名称  
 **✓ DO** 遵循命名类型派生自或实现某些.NET Framework 类型时下表中所述的指南。  
  
|基类型|派生/实现类型准则|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ DO** 将后缀"属性"添加到自定义特性类的名称。|  
|`System.Delegate`|**✓ DO** 将后缀"EventHandler"添加到的事件中使用的委托的名称。<br /><br /> **✓ DO** 添加之外作为事件处理程序使用的后缀"Callback"的名称的委托。<br /><br /> **X DO NOT** 将后缀"委托"添加到委托。|  
|`System.EventArgs`|**✓ DO** 添加后缀"EventArgs。"|  
|`System.Enum`|**X DO NOT** 从此类派生; 使用改为支持你的语言关键字; 例如，在 C# 中，使用`enum`关键字。<br /><br /> **X DO NOT** 添加后缀"枚举"或"标志"。|  
|`System.Exception`|**✓ DO** 添加后缀"异常"。|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ DO** 添加后缀"字典。" 请注意，`IDictionary`是特定类型的集合，但这一准则将优先于后面的更多常规集合准则。|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ DO** 添加后缀"集合"。|  
|`System.IO.Stream`|**✓ DO** 添加后缀"流"。|  
|`CodeAccessPermission IPermission`|**✓ DO** 添加后缀"权限。"|  
  
## <a name="naming-enumerations"></a>命名枚举  
 一般情况下 （也称为枚举） 的枚举类型的名称应遵循的标准类型命名规则 （PascalCasing 等）。 但是，有专门适用于枚举的其他指导原则。  
  
 **✓ DO** 使用枚举的单数形式的类型名称，除非其值是位域。  
  
 **✓ DO** 使用位域的枚举的复数形式的类型名称将用作值，也称为标志枚举。  
  
 **X DO NOT** 在枚举类型名称中使用"枚举"后缀。  
  
 **X DO NOT** 使用"标志"或"标志"后缀枚举中的键入名称。  
  
 **X DO NOT** 针对多格式文本枚举等使用枚举值名称 (例如，"ad"对 ADO 枚举。)、"rtf"上的前缀。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
