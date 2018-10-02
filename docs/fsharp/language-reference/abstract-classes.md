---
title: 抽象类 (F#)
description: '了解有关 F # 抽象类，这将部分或全部成员未实现和表示的一组不同的对象类型的常见功能。'
ms.date: 05/16/2016
ms.openlocfilehash: 7e1bb9daca7e8a3b442cd7fb02ef99bb6a2085cb
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43745445"
---
# <a name="abstract-classes"></a>抽象类

*抽象类*是留部分或全部成员未实现，以便可以由派生类提供实现的类。

## <a name="syntax"></a>语法

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>备注

在面向对象的编程中，抽象类用作基类的层次结构中，并表示一组不同的对象类型的常见功能。 正如所示名称"抽象"，抽象类通常并不对应直接到问题域中的具体实体上。 但是，它们代表多个不同的具体实体具有共同点。

抽象类必须具有`AbstractClass`属性。 它们可以实现和尚未实现的成员。 使用术语*抽象*时应用于类是与其他.NET 语言; 中的相同但是，使用术语*抽象*时应用于方法 （和属性） 是稍有不同在 F # 从其在其他.NET 语言中使用。 在 F # 中的方法标记为当`abstract`关键字，这指示成员具有一个项，称为*虚拟调度槽*，该类型的虚函数的内部表中。 换而言之，方法是虚拟的尽管`virtual`F # 语言中未使用关键字。 关键字`abstract`虚拟方法，而不考虑是否实现该方法上使用。 虚拟调度槽的声明是独立于为该调度槽方法的定义。 因此，虚拟方法声明和定义中另一种.NET 语言的 F # 等效项是抽象方法声明和使用的单独定义的组合`default`关键字或`override`关键字。 有关详细信息和示例，请参阅[方法](members/methods.md)。

一个类都被视为仅当存在的抽象方法声明但未定义的抽象。 因此，具有抽象方法的类不一定是抽象类。 除非类有未定义的抽象方法，否则不要使用**AbstractClass**属性。

在上述语法中，*可访问性修饰符*可以是`public`，`private`或`internal`。 有关详细信息，请参阅[访问控制](access-control.md)。

与其他类型一样，抽象类可以具有一个基类和一个或多个基接口。 每个基类或接口显示在单独的行一起使用`inherit`关键字。

一个抽象类的类型定义可以包含完全定义的成员，但它也可以包含抽象成员。 抽象成员的语法是单独显示在前面的语法。 在此语法中，*类型签名*的成员一个列表，其中包含的参数顺序和返回类型，类型分隔`->`令牌和/或`*`令牌作为相应的科里化和元组形式参数。 抽象成员类型签名的语法是在签名文件中使用和 intellisense Visual Studio 代码编辑器中显示的相同。

下面的代码演示一个抽象类形状，它具有两个非抽象派生的类，正方形和圆。 该示例演示如何使用抽象类、 方法和属性。 在示例中，抽象类形状表示的具体实体圆形和正方形的常用元素。 （在二维坐标系统） 的所有形状的常见功能都抽象到 Shape 类： 网格、 旋转的角度和面积和周长属性上的位置。 这些可以重写，但位置，其中各个形状不能更改的行为除外。

旋转方法可以重写的如下所示圆形类中，由于其对称性是固定的旋转。 因此在圆形类中，旋转方法被替换为不执行任何操作的方法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**输出：**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>请参阅

- [类](classes.md)
- [成员](members/index.md)
- [方法](members/methods.md)
- [属性](members/Properties.md)
