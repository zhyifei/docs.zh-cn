---
title: 扩展方法
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46539156"
---
# <a name="extension-methods"></a>扩展方法
扩展方法是一种语言功能，允许使用实例方法调用语法来调用静态方法。 这些方法必须采用至少一个参数，它表示的方法是在上运行的实例。  
  
 定义此类扩展方法的类称为"发起人"类，并且它必须声明为静态。 若要使用的扩展方法，其中一个必须导入定义主办方类的命名空间。  
  
 **X AVOID** frivolously 尤其是在你拥有的类型上定义扩展方法。  
  
 如果您是一种类型的源代码，请考虑改为使用常规的实例方法。 如果你拥有，并且你想要添加一个方法，要非常小心。 扩展方法的自由使用有可能会干扰 Api 旨在不具有这些方法的类型。  
  
 **✓ CONSIDER** 任何以下方案中使用扩展方法：  
  
-   若要提供的帮助器功能与每个接口的实现，如果说是功能可以编写方面的核心接口。 这是因为具体实现否则不能分配给接口。 例如，`LINQ to Objects`运算符作为扩展方法实现所有<xref:System.Collections.Generic.IEnumerable%601>类型。 因此，任何`IEnumerable<>`实现是自动启用 LINQ 的。  
  
-   实例方法时将引入依赖于某些类型，但此类依赖项将会破坏依赖项管理规则。 例如，依赖项从<xref:System.String>到<xref:System.Uri?displayProperty=nameWithType>可能是不可取，，因此`String.ToUri()`返回的实例方法`System.Uri`会从依赖关系管理角度来看了错误的设计。 静态扩展方法`Uri.ToUri(this string str)`返回`System.Uri`是多更好的设计。  
  
 **X AVOID** 上定义的扩展方法<xref:System.Object?displayProperty=nameWithType>。  
  
 VB 用户不能使用扩展方法语法的对象引用上调用此类方法。 VB 不支持调用此类方法，因为在 VB 中声明一个引用，因为对象会强制其将晚上的所有方法调用绑定 （名为的实际成员确定在运行时），而在 （提前编译时确定绑定到扩展方法绑定到的）。  
  
 请注意，该原则适用于其他语言相同的绑定行为是存在，或不支持的扩展方法。  
  
 **X DO NOT** 置于扩展的类型相同的命名空间的扩展方法，除非它是为添加到接口的方法或依赖关系管理。  
  
 **X AVOID** 定义两个或多个具有相同签名的扩展方法，即使它们驻留在不同的命名空间。  
  
 **✓ CONSIDER** 在扩展的类型相同的命名空间中定义的扩展方法，如果类型是接口，并且扩展方法为了在大多数或所有情况下使用。  
  
 **X DO NOT** 定义在与其他功能正常关联的命名空间中实现功能的扩展方法。 相反，它们属于该功能关联的命名空间中定义它们。  
  
 **X AVOID** 泛型命名的命名空间专用于扩展方法 （例如，"扩展"）。 使用描述性的名称 （例如，"路由"） 相反。  
  
 *部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
