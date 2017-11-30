---
title: "类型成员的名称"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1a3460b734d5bab6f5362fa9d3631e06821f6d49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-type-members"></a>类型成员的名称
类型由的成员： 方法、 属性、 事件、 构造函数和字段。 以下各节描述了命名类型成员的准则。  
  
## <a name="names-of-methods"></a>方法名称  
 由于方法的执行操作的方法，但设计准则要求方法名称是谓词或谓词短语。 也遵循这一准则选项可用于将方法名称区分开来的属性和类型名称，它们是名词或形容词短语。  
  
 **✓ 执行**谓词或谓词短语的方法的名称。  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>属性名称  
 与其他成员不同属性应为名词短语或形容词名称。 这是因为属性指数据，并且属性的名称将反映出的。 PascalCasing 始终用于属性名称。  
  
 **✓ 执行**用名词、 名词短语或形容词命名属性。  
  
 **X 不**具有一些属性，如以下示例所示的"Get"方法的名称匹配：  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 此模式通常指示该属性应实际上是一种方法。  
  
 **✓ 执行**具有描述而不是使用单数短语跟"列表"或"集合"。 集合中的项的复数形式短语名称集合属性  
  
 **✓ 执行**名称与赞成短语的布尔型属性 (`CanSeek`而不是`CantSeek`)。 （可选） 还前缀布尔型属性使用"Is"，"可以"或"具有，"但仅在它增添价值。  
  
 **请考虑 ✓**指定相同的名称作为其类型的属性。  
  
 例如，以下属性正确获取和设置名为枚举值`Color`，因此该属性名为`Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>事件的名称  
 始终引用某一操作，是指位于发生或一个已发生事件。 因此，与方法一样，事件名称中带有谓词，并且谓词时态用于指示何时引发事件的时间。  
  
 **✓ 执行**命名事件的谓词或谓词短语。  
  
 示例包括`Clicked`， `Painting`， `DroppedDown`，依次类推。  
  
 **✓ 执行**为提供了事件名称的概念与之前和之后，使用现在时或过去时态。  
  
 例如，将调用关闭窗口之前引发的关闭事件`Closing`，并将调用其中一个时段结束后引发`Closed`。  
  
 **X 不**使用"Before"或"After"前缀或 postfixes 以指示预和后期事件。 使用存在和过去时态如上所述。  
  
 **✓ 执行**具有"EventHandler"后缀，名称事件处理程序 （委托用作事件类型），如下面的示例中所示：  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ 执行**使用两个参数名为`sender`和`e`在事件处理程序。  
  
 发件人参数表示引发事件的对象。 发件人参数的类型通常是`object`，即使它也可使用更具体的类型。  
  
 **✓ 执行**命名自变量类与"EventArgs"后缀的事件。  
  
## <a name="names-of-fields"></a>字段的名称  
 字段命名准则适用于静态的公共和受保护字段。 内部和私有字段未涵盖的准则，和公共或受保护的实例字段都不允许的[成员设计准则](../../../docs/standard/design-guidelines/member.md)。  
  
 **✓ 执行**在字段名称中使用 PascalCasing。  
  
 **✓ 执行**命名字段使用名词、 名词短语或形容词。  
  
 **X 不**字段名称中使用前缀。  
  
 例如，不要使用"g_"或"s_"以指示静态字段。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>另请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
 [命名规则](../../../docs/standard/design-guidelines/naming-guidelines.md)
