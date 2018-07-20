---
title: 类型成员的名称
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25fe93b63c518f54ee72300f26dfcb3f3ad21d76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575344"
---
# <a name="names-of-type-members"></a>类型成员的名称
类型由成员组成： 方法、 属性、 事件、 构造函数和字段。 以下各节描述了命名类型成员的准则。  
  
## <a name="names-of-methods"></a>方法名称  
 因为方法意味着执行操作，所以设计准则要求方法名称是谓词或谓词短语。 遵循本准则还可以区分方法名称与属性和类型名称，即名词或形容词短语。
  
 **✓ 要**使用谓词或谓词短语作为方法的名称。  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>属性名称  
 与其他成员不同，属性应为名词短语或形容词名称。 这是因为属性引用数据，并且属性的名称也反映了这一点。 始终将 PascalCasing 用于属性名称。  
  
 **✓ 要**用名词、 名词短语或形容词命名属性。  
  
 **X 不要**具有与"Get"方法的名称匹配的属性，如以下示例所示：  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 此模式通常表明该属性应实际上是一种方法。  
  
 **✓ 要**使用描述集合中项目的复数短语命名集合属性，而不是使用单个短语，后跟“List”或“Collection”。 
  
 **✓ 要**使用肯定短语命名布尔型属性 (`CanSeek`而不是`CantSeek`)。 或者，还可以使用前缀"Is"，"Can"或"Has"为布尔型属性添加前缀，但仅在它有意义的位置。  
  
 **✓ 考虑**给予属性与其类型相同的名称。
  
 例如，以下属性正确获取并设置名为`Color`的枚举值，因此该属性名为`Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>事件的名称  
 事件总是指某个动作，无论是正在发生的动作还是已经发生的动作。 因此，与方法一样，事件用谓词命名，谓词时态用于指示事件引发的时间。 
  
 **✓ 要**使用谓词或谓词短语命名事件。  
  
 示例包括`Clicked`， `Painting`， `DroppedDown`，等等。  
  
 **✓ 要**使用现在和过去时态，给予事件名称前后的概念。
  
 例如，将窗口关闭之前引发的事件称为`Closing`，而在窗口关闭之后引发的事件被称为`Closed`。  
  
 **X 不要**使用“Before”或“After”前缀和后缀来指示事件的前后。 使用刚刚描述的当前和过去时态。
  
 **✓ 要**使用“EventHandler”后缀命名事件处理程序（用作事件类型的委托），如以下示例所示： 
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ 要**在事件处理程序中使用两个名为`sender`和`e`的参数。  
  
 sender参数表示引发事件的对象。 sender参数的类型通常是`object`，但也可使用更具体的类型。  
  
 **✓ 要**使用"EventArgs"后缀命名事件参数类。  
  
## <a name="names-of-fields"></a>字段的名称  
 字段命名准则适用于静态公共字段和受保护字段。 准则不包含内部和私有字段，[成员设计准则](../../../docs/standard/design-guidelines/member.md)不允许使用公共或受保护的实例字段。
  
 **✓ 要**在字段名称中使用 PascalCasing。  
  
 **✓ 要**使用名词、 名词短语或形容词命名字段。  
  
 **X 不要**在字段名称中使用前缀。  
  
 例如，不要使用"g_"或"s_"来指示静态字段。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*
  
 *由 Pearson Education, Inc 许可，转载自[Framework 设计准则： 可重用.NET 库的约定、 惯用法和模式 第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者 Krzysztof Cwalina 和 Brad Abrams，由Addison Wesley Professional 于 2008 年 10 月 22 日发布，作为 Microsoft Windows 开发系列的一部分。
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
