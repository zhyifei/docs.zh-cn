---
title: 访问控制 (F#)
description: '了解如何控制到编程元素，如类型、 方法和函数，F # 编程语言中的访问。'
ms.date: 05/16/2016
ms.openlocfilehash: 0a5cc1faa1aef343aaca0abb0c42a0dd9a52fcbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="access-control"></a>访问控制

*访问控制*指声明哪些客户端可以使用程序的特定元素，如类型、 方法和函数。


## <a name="basics-of-access-control"></a>访问控制的基础知识
在 F # 中，将访问控制说明符`public`， `internal`，和`private`可以应用于模块、 类型、 方法、 值定义、 函数、 属性和显式字段。


- `public` 指示所有调用方可以访问该实体。

- `internal` 指示该实体，可以访问只能从同一程序集。

- `private` 指示该实体，可以访问只能从封闭类型或模块。


>[!NOTE] 
访问说明符`protected`不用在 F # 中，尽管它是可接受的如果你使用的在支持的语言中编写的类型`protected`访问。 因此，如果你重写的受保护的方法，仍然只能在类及其后代中访问你的方法。

一般情况下，使用说明符放在前面的实体，除非`mutable`或`inline`使用说明符时，在访问控制说明符后显示的哪一。

如果使用没有访问说明符时，默认值是`public`，除`let`类型中的绑定，后者始终是`private`为的类型。

F # 中的签名提供另一种机制，用于控制对 F # 程序元素的访问。 签名不需要的访问控制。 有关详细信息，请参阅[签名](signatures.md)。


## <a name="rules-for-access-control"></a>访问控制规则
访问控制是需遵循以下规则：


- 继承声明 (即，使用`inherit`指定的类的基类)、 接口声明 （即，指定类将实现接口），和抽象成员始终具有与封闭类型相同的可访问性。 因此，这些构造不能用于访问控制说明符。

- 可区分联合中的各个事例不能具有自己独立于联合类型的访问控制修饰符。

- 每个字段的记录类型不能具有自己独立于记录类型的访问控制修饰符。


## <a name="example"></a>示例
下面的代码演示如何使用访问控制说明符。 在项目中，有两个文件`Module1.fs`和`Module2.fs`。 每个文件隐式是一个模块。 因此，有两个模块，`Module1`和`Module2`。 中的私有类型和内部类型的定义`Module1`。 不能从访问私有类型`Module2`，但可以将内部类型。

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
下面的代码测试中创建的类型的可访问性`Module1.fs`。

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a>请参阅
[F# 语言参考](index.md)

[签名](signatures.md)
