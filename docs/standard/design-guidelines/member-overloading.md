---
title: 成员重载
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2127497d294cbfd4e1bb24d033f432378627ff13
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964197"
---
# <a name="member-overloading"></a>成员重载
成员重载意味着在同一类型上创建两个或多个成员，这些成员仅在参数的数量或类型上有所不同，但具有相同的名称。例如，在下面的代码中，`WriteLine` 方法被重载：

```
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```

因为只有方法，构造函数和索引属性可以有参数，所以只有这些成员可以进行重载。

重载是提高可重用库的可用性、生产力和可读性的最重要的技术之一。对参数数量的重载可以提供更简单的构造函数和方法版本。对参数类型进行重载可以对在选定的一组不同类型上执行相同操作的成员使用相同的成员名称。
  
**✓ 务必** 尝试使用描述性参数名称来表示较短重载使用的默认值。

**X 避免** 在重载中随意改变参数名称。如果一个重载中的参数与另一个重载中的参数表示相同的输入，则这些参数应具相同的名称。

**X 避免** 对重载成员中的参数使用不一致的排序。具有相同名称的参数应出现在所有重载中的相同位置。

**✓ 务必** 仅使最长的重载成为虚拟方法（如果可扩展性是必需的）。较短的重载应该简单地调用较长的重载。

**X 切忌** 使用 `ref` 或 `out` 修饰符来重载成员。  

有些语言无法解析对此类重载的调用。此外，此类重载通常具有完全不同的语义，可能不应该是重载，而是两个单独的方法。

**X 切忌** 在重载中设置相同位置和相似类型但具有不同的语义的参数。

**✓ 务必** 允许为可选参数传递 `null`。  

**✓ 务必** 使用成员重载而不是定义使用默认参数的成员。

默认参数不符合 CLS。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
