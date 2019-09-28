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
ms.openlocfilehash: 4caa0ae78d168b23fd2862153bef0e3960d3ea42
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392946"
---
# <a name="member-overloading"></a>成员重载
成员重载意味着在同一类型上创建两个或多个成员，这些成员仅在参数的数量或类型中不同，但具有相同的名称。 例如，在下面的中，将重载 `WriteLine` 方法：  
  
```csharp  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 由于只有方法、构造函数和索引属性可以有参数，因此只能重载这些成员。  
  
 重载是提高可重用库的可用性、生产力和可读性的最重要方法之一。 参数数量重载使您可以提供更简单的构造函数和方法版本。 使用参数类型的重载，可以为在所选的不同类型集上执行相同操作的成员使用相同的成员名称。  
  
 **✓ 务必** 尝试使用描述性的参数名称以指示较短的重载使用的默认值。  
  
 **X 避免** 随意更改重载中的参数名称。 如果一个重载中的参数表示与另一个重载中的参数相同的输入，则这些参数应具有相同的名称。  
  
 **X 避免** 在排序中的参数中不一致状态重载成员。 具有相同名称的参数应出现在所有重载的同一位置。  
  
 **✓ 务必** 使只有最长的重载成为虚方法 （如果可扩展性是必需的）。 更短的重载只需调用更长的重载。  
  
 **X 切忌** 使用`ref`或`out`修饰符来重载成员。  
  
 某些语言无法解析对重载的调用。 此外，此类重载通常具有完全不同的语义，但可能不应作为重载，而是使用两种不同的方法。  
  
 **X 切忌** 具有重载随着在相同的位置以及相似类型的参数，而使用不同的语义。  
  
 **✓ 务必** 允许`null`要为可选自变量传递。  
  
 **✓ 务必** 使用重载，而不是定义具有默认自变量的成员的成员。  
  
 默认参数不符合 CLS。  
  
 *部分版权 © 2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*  
  
## <a name="see-also"></a>请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
