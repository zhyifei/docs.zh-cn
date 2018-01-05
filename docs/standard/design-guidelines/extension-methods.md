---
title: "扩展方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 28ce4451f9f8cc634ab76b3b4ef845103ea55e35
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="extension-methods"></a>扩展方法
扩展方法是允许使用实例方法调用语法来调用静态方法的语言功能。 这些方法必须采用至少一个参数，它表示的方法是在上运行的实例。  
  
 定义此类扩展方法的类称为"发起人"类，并必须声明为静态。 若要使用扩展方法，其中一个必须导入定义发起人类的命名空间。  
  
 **请避免 x** frivolously 尤其是在你拥有的类型上定义扩展方法。  
  
 如果你拥有的一种类型的源代码，请考虑改为使用常规的实例方法。 如果你拥有，并且你想要添加一个方法，保持谨慎。 扩展方法的自由使用有可能会干扰的没有设计具有这些方法的类型的 Api。  
  
 **请考虑 ✓**任何以下方案中使用扩展方法：  
  
-   若要提供的帮助器功能相关的每个实现的接口，如果功能可以编写在核心接口方面。 这是因为具体实现否则不能分配到接口。 例如，`LINQ to Objects`运算符作为扩展方法实现所有<xref:System.Collections.Generic.IEnumerable%601>类型。 因此，任何`IEnumerable<>`实现是自动启用 LINQ 的。  
  
-   依赖于某个类型，但这种相关性的实例方法将会带来时将会破坏依赖关系管理规则。 例如，依赖项从<xref:System.String>到<xref:System.Uri?displayProperty=nameWithType>可能是不可取，因此`String.ToUri()`返回的实例方法`System.Uri`依赖项管理角度错误设计非常。 静态的扩展方法`Uri.ToUri(this string str)`返回`System.Uri`将多更好的设计。  
  
 **请避免 x**上定义的扩展方法<xref:System.Object?displayProperty=nameWithType>。  
  
 VB 用户不能调用使用扩展方法语法的对象引用此类方法。 VB 不支持调用此类方法，因为在 VB 中将引用声明为对象将强制所有方法调用，它是后期绑定 （名为的实际成员确定在运行时），而在 （尽早编译时确定绑定到扩展方法绑定）。  
  
 请注意，那么准则适用于其他语言相同的绑定行为是存在，或不支持扩展方法。  
  
 **X 不**置于扩展的类型相同的命名空间的扩展方法，除非它是为添加到接口的方法或依赖关系管理。  
  
 **请避免 x**定义两个或多个具有相同签名的扩展方法，即使它们驻留在不同的命名空间。  
  
 **请考虑 ✓**在扩展的类型相同的命名空间中定义的扩展方法，如果类型是接口，并且扩展方法为了在大多数或所有情况下使用。  
  
 **X 不**定义在与其他功能正常关联的命名空间中实现功能的扩展方法。 相反，在它们所属的功能与关联的命名空间中定义它们。  
  
 **请避免 x**泛型命名的命名空间专用于扩展方法 （例如，"扩展"）。 使用描述性的名称 （例如，"路由"） 相反。  
  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
