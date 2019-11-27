---
title: 继承的基础知识
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350824"
---
# <a name="inheritance-basics-visual-basic"></a>继承的基础知识 (Visual Basic)

`Inherits` 语句用于声明一个名为*派生类*的新类，该类基于现有类（称为*基类*）。 派生类继承和可以扩展基类中定义的属性、方法、事件、字段和常量。 以下部分介绍了一些继承规则，以及可用于更改类继承或继承方式的修饰符：

- 默认情况下，所有类都是可继承的，除非使用 `NotInheritable` 关键字进行标记。 类可以继承自你的项目中的其他类，也可以来自你的项目引用的其他程序集中的类。

- 与允许多重继承的语言不同，Visual Basic 只允许在类中进行单一继承;也就是说，派生类只能有一个基类。 尽管类中不允许使用多个继承，但类可实现多个接口，这些接口可以有效地实现相同的结束。

- 若要防止公开基类中的受限制项，派生类的访问类型必须等于或大于其基类的限制。 例如，`Public` 类无法继承 `Friend` 或 `Private` 类，并且 `Friend` 类不能继承 `Private` 类。

## <a name="inheritance-modifiers"></a>继承修饰符

Visual Basic 引入了以下类级语句和修饰符来支持继承：

- `Inherits` 语句—指定基类。

- `NotInheritable` 修饰符-阻止程序员使用类作为基类。

- `MustInherit` 修饰符-指定类仅用作基类。 不能直接创建 `MustInherit` 类的实例;它们只能作为派生类的基类实例来创建。 （其他编程语言（例如C++和C#）使用字词*抽象类*来描述此类。）

## <a name="overriding-properties-and-methods-in-derived-classes"></a>重写派生类中的属性和方法

默认情况下，派生类继承其基类的属性和方法。 如果继承的属性或方法在派生类中具有不同的行为，则可以将其*重写*。 也就是说，您可以在派生类中定义方法的新实现。 下列修饰符用于控制如何重写属性和方法：

- `Overridable`-允许在派生类中重写类中的属性或方法。

- `Overrides`-重写基类中定义的 `Overridable` 属性或方法。

- `NotOverridable`-防止在继承类中重写属性或方法。 默认情况下，将 `NotOverridable``Public` 方法。

- `MustOverride`-要求派生类重写属性或方法。 使用 `MustOverride` 关键字时，方法定义只包含 `Sub`、`Function`或 `Property` 语句。 不允许使用其他语句，特别是没有 `End Sub` 或 `End Function` 语句。 `MustOverride` 方法必须在 `MustInherit` 类中声明。

假设您要定义用于处理工资单的类。 您可以定义一个泛型 `Payroll` 类，该类包含计算典型周工资单的 `RunPayroll` 方法。 然后，可以使用 `Payroll` 作为更专业化 `BonusPayroll` 类的基类，这些类可在分发员工奖金时使用。

`BonusPayroll` 类可以继承和重写在基本 `Payroll` 类中定义的 `PayEmployee` 方法。

下面的示例定义了一个基类，`Payroll,` 和一个派生类 `BonusPayroll`，后者重写继承的方法 `PayEmployee`。 `RunPayroll`，将创建一个 `Payroll` 对象，然后将 `BonusPayroll` 对象传递到执行两个对象的 `PayEmployee` 方法的函数 `Pay`。

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>MyBase 关键字

`MyBase` 关键字的行为类似于引用类的当前实例的基类的对象变量。 `MyBase` 经常用于访问派生类中被重写或隐藏的基类成员。 具体而言，`MyBase.New` 用于从派生类构造函数中显式调用基类构造函数。

例如，假设您正在设计一个派生类，该派生类重写从基类继承的方法。 重写的方法可以调用基类中的方法并修改返回值，如下面的代码段所示：

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

以下列表描述了使用 `MyBase`的限制：

- `MyBase` 指的是直接基类及其继承的成员。 它不能用于访问类中的 `Private` 成员。

- `MyBase` 是关键字，而不是实际对象。 不能将 `MyBase` 分配给变量、传递给过程或用于 `Is` 比较。

- 无需在直接基类中定义 `MyBase` 限定的方法;可以改为在间接继承基类中定义它。 为了使 `MyBase` 限定的引用正确编译，某些基类必须包含与调用中显示的参数的名称和类型匹配的方法。

- 不能使用 `MyBase` 调用 `MustOverride` 基类方法。

- `MyBase` 不能用于限定自身。 因此，以下代码无效：

  `MyBase.MyBase.BtnOK_Click()`

- 不能在模块中使用 `MyBase`。

- 如果基类在不同的程序集中，`MyBase` 不能用于访问标记为 `Friend` 的基类成员。

有关详细信息和其他示例，请参阅[如何：访问被派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。

## <a name="the-myclass-keyword"></a>MyClass 关键字

`MyClass` 关键字的行为类似于引用最初实现的类的当前实例的对象变量。 `MyClass` 类似于 `Me`，但 `MyClass` 上的每个方法和属性调用都被视为[NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)方法或属性。 因此，方法或属性不受派生类中重写的影响。

- `MyClass` 是关键字，而不是实际对象。 不能将 `MyClass` 分配给变量、传递给过程或用于 `Is` 比较。

- `MyClass` 引用包含类及其继承成员。

- `MyClass` 可以用作 `Shared` 成员的限定符。

- `MyClass` 不能用于 `Shared` 方法中，但可以在实例方法内部使用以访问类的共享成员。

- `MyClass` 不能用于标准模块。

- `MyClass` 可用于限定在基类中定义的方法，该方法没有该类中提供的方法的实现。 此类引用与 `MyBase.`*方法*具有相同的含义。

下面的示例将 `Me` 和 `MyClass`进行比较。

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

即使 `derivedClass` 重写 `testMethod`，`useMyClass` 中的 `MyClass` 关键字 nullifies 重写的效果，并且编译器解析对 `testMethod`的基类版本的调用。

## <a name="see-also"></a>另请参阅

- [Inherits 语句](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
