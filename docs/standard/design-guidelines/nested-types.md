---
title: 嵌套类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- types, nested
- public nested types
- type design guidelines, nested types
- nested types
- members [.NET Framework], type
- class library design guidelines [.NET Framework], nested types
ms.assetid: 12feb7f0-b793-4d96-b090-42d6473bab8c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2593b85dd4747a3fbe365994c3e5d9beae3e3406
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188134"
---
# <a name="nested-types"></a>嵌套类型
嵌套类型是在另一种类型的范围内定义的类型，称为封闭类型。嵌套类型可以访问其封闭类型的所有成员。例如，它可以访问在封闭类型中定义的私有字段以及在封闭类型的所有祖先中定义的受保护字段。

一般情况下，应谨慎使用嵌套类型。有以下几个原因。一些开发人员并不完全熟悉这个概念。例如，这些开发人员可能在声明嵌套类型变量的语法方面存在问题。嵌套类型也与它们的封闭类型紧密耦合，因此不适合作为通用类型。

嵌套类型最适合其封闭类型的建模实现细节。最终用户应该很少声明嵌套类型的变量，并且几乎从不用显式实例化嵌套类型。例如，集合的枚举器可以是该集合的嵌套类型。枚举器通常由它们的封闭类型实例化，并且因为许多语言都支持 foreach 语句，所以枚举变量很少由最终用户声明。

**✓ 务必**当嵌套类型与其外部类型之间的关系需要成员可访问性语义时，使用嵌套类型。

**X 切忌**使用公共嵌套类型作为逻辑分组结构；对此情况要使用名称空间。

**X 避免**公开暴露嵌套类型。唯一的例外是，嵌套类型的变量需要在极少数情况下进行声明，例如子类化或其他高级自义方案。

**X 切忌**使用嵌套类型（如果可能在包含类型之外引用类型）。

例如，传递给类上定义的方法的枚举不应该被定义为类中的嵌套类型。

**X 切忌**使用嵌套类型（如果它们需要通过客户端代码实例化）。如果类型具有公共构造函数，则它可能不应该被嵌套。

如果类型可以被实例化，那表明该类型在框架中占有一席之地（你可以创建它、使用它，并在不使用外部类型的情况下销毁它），因此不应该嵌套。内部类型不应在与外部类型无任何关系的情况下在外部类型之外广泛重用。
  
**X 切忌** 将嵌套类型定义为接口的成员。许多语言不支持此类结构。
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。* 

*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [类型设计准则](../../../docs/standard/design-guidelines/type.md)  
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
