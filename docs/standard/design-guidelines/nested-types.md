---
title: 嵌套类型
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
ms.openlocfilehash: 3467851aa767efcd0557e8a412cd36316a48b9b0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709148"
---
# <a name="nested-types"></a>嵌套类型
嵌套类型是在另一种类型的作用域内定义的类型，称为封闭类型。 嵌套类型可以访问其封闭类型的所有成员。 例如，它可以访问在封闭类型中定义的私有字段，还可以访问在封闭类型的所有祖先中定义的受保护字段。  
  
 一般而言，应慎用嵌套类型。 其原因有若干： 有些开发人员并不完全熟悉该概念。 例如，这些开发人员可能遇到声明嵌套类型变量的语法问题。 嵌套类型也与它们的封闭类型紧密耦合，因此不适合用作通用类型。  
  
 嵌套类型最适合用于建模其封闭类型的实现细节。 最终用户极少需要声明嵌套类型的变量，几乎不应显式实例化嵌套类型。 例如，集合的枚举器可以是该集合的嵌套类型。 枚举器通常通过其封闭类型进行实例化，由于许多语言支持 foreach 语句，因此枚举器变量很少需要由最终用户声明。  
  
 **✓ DO** 使用嵌套的类型，从而使成员可访问性语义都需要的嵌套的类型和其外部类型之间的关系时。  
  
 **X 切忌** 使用公共嵌套的类型作为自己的逻辑分组构造; 为此使用命名空间。  
  
 **X 避免** 公共公开嵌套的类型。 唯一的例外是，只需在很少的情况下（如子类化或其他高级自定义方案）声明嵌套类型的变量。  
  
 **X 切忌** 使用嵌套的类型，如果类型为可能包含类型的外部引用。  
  
 例如，传递给在类上定义的方法的枚举不应定义为类中的嵌套类型。  
  
 **X 切忌** 使用嵌套的类型，如果他们需要通过客户端代码来实例化。  如果某个类型具有公共构造函数，则它可能不会嵌套。  
  
 如果可实例化类型，则似乎指示类型在框架中具有一个位置（你可以创建它、使用它，并在不使用外部类型的情况下销毁它），因此不应进行嵌套。 不应将内部类型广泛地在外部类型的外部重用，无需任何与外部类型的关系。  
  
 **X 切忌** 定义为接口成员的嵌套的类型。 许多语言不支持这种构造。  
  
 *部分©2005，2009 Microsoft Corporation。保留所有权利。*  
  
 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。  
  
## <a name="see-also"></a>另请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
