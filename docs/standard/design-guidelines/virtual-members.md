---
title: 虚成员
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 2c1e6d9aeafa1c9d7ee4b0c2c626b6fd7be6cf99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708966"
---
# <a name="virtual-members"></a>虚成员
可以重写虚拟成员，从而改变子类的行为。 就提供的可扩展性而言，它们与回调非常相似，但在执行性能和内存消耗方面有更好的表现。 此外，虚拟成员在需要创建特殊类型的现有类型（特化）的场景中感觉更自然。  
  
 虚拟成员的性能优于回调和事件，但不如非虚拟方法。  
  
 虚拟成员的主要缺点是虚拟成员的行为只能在编译时修改。 回调的行为可以在运行时修改。  
  
 虚拟成员，如回调（可能不仅仅是回调），其设计、测试和维护成本很高，因为对虚拟成员的任何调用都可能以不可预测的方式重写，并且可以执行任意代码。 此外，通常需要更多的努力来明确定义虚拟成员的协定，因此设计和记录它们的成本更高。  
  
 **X 切忌** 使用虚拟成员，除非你有充分的理由这样做，并且了解与设计、测试和维护虚拟成员相关的所有成本。  
  
 在不破坏兼容性的情况下，不容易对虚拟成员进行更改。 此外，它们比非虚拟成员慢，主要是因为对虚拟成员的调用不是内联的。  
  
 **✓ CONSIDER** 限制只将绝对必要的扩展性。  
  
 **✓ 务必** 对于虚拟成员，更倾向使用受保护的可访问性而非公共可访问性。 公共成员应通过调用受保护的虚拟成员来提供可扩展性（如果需要）。  
  
 一个类的公共成员应该为该类的直接使用者提供正确的功能集。 根据设计，虚拟成员在子类中被重写。受保护的可访问性是一种很好的方式，可以将所有虚拟扩展点限定在可以使用它们的地方。  
  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [扩展性设计](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
