---
title: 成员重载
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
author: KrzysztofCwalina
ms.openlocfilehash: 93b294c4b535e015c7f4b021e0f950f038a60361
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152430"
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
  
 **✓ 务必** 尝试使用描述性的参数名称以指示较短的重载使用的默认值。  

 **X 避免** 随意更改重载中的参数名称。 如果某一重载中的参数表示相同的输入中的另一个重载的参数，参数应具有相同的名称。  

 **X 避免** 在排序中的参数中不一致状态重载成员。 具有相同名称的参数应出现在相同位置中所有重载。  

 **✓ 务必** 使只有最长的重载成为虚方法 （如果可扩展性是必需的）。 只需较短的重载应调用通过到较长的重载。  

 **X 切忌** 使用`ref`或`out`修饰符来重载成员。  

有些语言无法解析对此类重载的调用。此外，此类重载通常具有完全不同的语义，可能不应该是重载，而是两个单独的方法。

 **X 切忌** 具有重载随着在相同的位置以及相似类型的参数，而使用不同的语义。  

 **✓ 务必** 允许`null`要为可选自变量传递。  

 **✓ 务必** 使用重载，而不是定义具有默认自变量的成员的成员。  

默认参数不符合 CLS。

*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
 *通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
