---
title: 抽象类 (F#)
description: '了解有关 F # 抽象类，该类将保留未实现的部分或全部成员和表示的一组不同的对象类型的常见功能。'
ms.date: 05/16/2016
ms.openlocfilehash: c472e9d164ae78bde716bb5102e54f4e698b61b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562383"
---
# <a name="abstract-classes"></a>抽象类

*抽象类*是留部分或全部成员未实现，以便可以由派生类中提供实现的类。

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
在面向对象编程中，一个抽象类用作基类的层次结构，并表示的一组不同的对象类型的通用功能。 名称"抽象"可以看出，抽象类通常并不对应直接拖动到的问题域中的具体实体。 但是，它们表示许多不同的具体实体具有共同。

抽象类必须具有`AbstractClass`属性。 它们可以实现和尚未实现的成员。 使用术语*抽象*当应用于类是与其他.NET 语言; 中的相同但是，使用术语*抽象*当应用于方法 （和属性） 是稍有不同在 F # 从其在其他.NET 语言中使用。 在 F # 中，当的方法标记为`abstract`关键字，这指示成员有一个项，称为*虚拟调度槽*，该类型的虚拟函数的内部表中。 换而言之，方法是虚拟的虽然`virtual`F # 语言中未使用关键字。 关键字`abstract`无论是否实现该方法的虚拟方法上使用。 虚拟调度槽的声明是独立于为该调度槽方法的定义。 因此，虚拟方法声明和定义另一种.NET 语言的 F # 等价内容是一个抽象方法声明和独立的定义，使用的组合`default`关键字或`override`关键字。 有关详细信息和示例，请参阅[方法](members/methods.md)。

一个类都被视为抽象仅在没有抽象方法的声明但未定义。 因此，具有抽象方法的类并不一定是抽象类。 除非类具有未定义抽象方法，不要使用**AbstractClass**属性。

在上述语法中，*可访问性修饰符*可以是`public`，`private`或`internal`。 有关详细信息，请参阅[访问控制](access-control.md)。

与其他类型一样，抽象类可以具有的基类和一个或多个基接口。 每个基类或接口显示在单独的行连同`inherit`关键字。

一个抽象类的类型定义可以包含完全定义的成员，但它也可以包含抽象成员。 在上述语法中，抽象成员的语法是单独显示。 在此语法中，*类型签名*的成员的列表包含的参数类型中提供顺序和返回类型、 隔开`->`令牌和/或`*`扩充根据令牌和元组形式参数。 在签名文件中使用和 intellisense Visual Studio 代码编辑器中显示相同的抽象成员类型签名的语法。

下面的代码演示了一个抽象类形状，有两个非抽象派生的类，Square 和圆圈。 该示例演示如何使用抽象类、 方法和属性。 在示例中，抽象类形状表示常见元素的具体实体圆形和正方形。 （二维的坐标系统） 中的所有形状的常见功能都抽象到形状类： 网格、 旋转的角度和区域和外围属性上的位置。 这些可以重写，但位置，其中各个形状无法更改的行为除外。

旋转可以重写方法，如下所示 Circle 类，由于其对称性是固定的旋转。 因此在圆类中，旋转方法替换为不执行任何操作的方法。

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**输出：**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>请参阅
[类](classes.md)

[成员](members/index.md)

[方法](members/methods.md)

[属性](members/Properties.md)
