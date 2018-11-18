---
title: 扩展方法
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47396911"
---
# <a name="extension-methods"></a>扩展方法
扩展方法是一种语言特性，允许使用实例方法调用语法来调用静态方法。这些方法必须至少使用一个参数，该参数表示方法要操作的实例。

定义此类扩展方法的类称为 “sponsor” 类，必须将其声明为 static。要使用扩展方法，必须导入定义 sponsor 类的命名空间。
  
**X 避免** 轻率定义扩展方法，尤其是在您不拥有的类型上。  

如果您拥有该类型的源代码，请考虑使用常规实例方法。如果您没有，并且想要添加方法，请务必小心。随意使用扩展方法可能会使本来不具备这些方法的类型产生混乱的API。

**✓ 考虑** 在以下任何一种情况下使用扩展方法：  

- 提供与接口的每个实现相关的辅助功能，如果上述功能可以根据核心接口编写。这是因为不能将具体实现分配给接口。例如，`LINQ to Objects` 操作符为所有 <xref:System.Collections.Generic.IEnumerable%601> 类型被实现为扩展方法。因此，任何 `IEnumerable<>` 的实现都会自动启用LINQ。

- 当实例方法会在某种类型上引入依赖关系，但这样的依赖关系会破坏依赖关系管理规则的时候。例如，从 <xref:System.String> 至 <xref:System.Uri?displayProperty=nameWithType> 的依赖可能是不可取的，因此返回 `System.Uri` 的 `String.ToUri()` 实例方法从依赖管理的角度来看是错误的设计。一个返回 `System.Uri` 的静态扩展方法 `Uri.ToUri(this string str)` 将是一个更好的设计。

**X 避免** 在 <xref:System.Object?displayProperty=nameWithType> 上定义扩展方法。  
  
VB 用户将无法使用扩展方法语法在对象引用上调用此类方法。VB 不支持调用这样的方法，因为在 VB 中，将引用声明为 Object 会强制对其所有方法调用进行延迟绑定（在运行时确定调用的实际成员），而在编译时确定对扩展方法的绑定（早期绑定）。
  
请注意，该准则适用于存在相同绑定行为的其他语言，或者不支持扩展方法的其他语言。
  
**X 切忌** 将扩展方法放在与扩展类型相同的命名空间中，除非它是用于向接口添加方法或用于依赖关系管理。
  
**X 避免** 定义两个或多个具有相同名的扩展方法，即使它们位于不同的命空间中。

**✓ 考虑** 如果类型是接口，并且扩方法适用于大多数或所有情况，则在与展类型相同的命名空间中定义扩展方法。

**X 切忌** 在通常与其他功能相关联命名空间中定义实现某功能的扩展方法而是在与该功能相关联的命名空间中定它们。

**X 避免** 对命名空间使用专用于扩展方法的通用名称来命名（例如，“Extensions”）。请改为使用描述性名称（例如 “Routing”）。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
