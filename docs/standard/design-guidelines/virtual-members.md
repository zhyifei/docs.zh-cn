---
title: 가상 멤버
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 8ed519a01162056151d8ae6398c0d06495911afd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743528"
---
# <a name="virtual-members"></a>가상 멤버
可以重写虚拟成员，从而改变子类的行为。 就提供的可扩展性而言，它们与回调非常相似，但在执行性能和内存消耗方面有更好的表现。 此外，虚拟成员在需要创建特殊类型的现有类型（特化）的场景中感觉更自然。

 虚拟成员的性能优于回调和事件，但不如非虚拟方法。

 虚拟成员的主要缺点是虚拟成员的行为只能在编译时修改。 回调的行为可以在运行时修改。

 虚拟成员，如回调（可能不仅仅是回调），其设计、测试和维护成本很高，因为对虚拟成员的任何调用都可能以不可预测的方式重写，并且可以执行任意代码。 此外，通常需要更多的努力来明确定义虚拟成员的协定，因此设计和记录它们的成本更高。

 除非你有充分的理由，否则 ❌ 不要使成员成为虚拟成员，并且你知道与设计、测试和维护虚拟成员相关的所有成本。

 在不破坏兼容性的情况下，不容易对虚拟成员进行更改。 此外，它们比非虚拟成员慢，主要是因为对虚拟成员的调用不是内联的。

 ✔️考虑将扩展性限制为仅绝对必要的。

 ✔️比虚拟成员的公共可访问性更喜欢受保护的可访问性。 公共成员应通过调用受保护的虚拟成员来提供可扩展性（如果需要）。

 一个类的公共成员应该为该类的直接使用者提供正确的功能集。 根据设计，虚拟成员在子类中被重写。受保护的可访问性是一种很好的方式，可以将所有虚拟扩展点限定在可以使用它们的地方。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>另请参阅

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
