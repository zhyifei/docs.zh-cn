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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401459"
---
# <a name="inheritance-basics-visual-basic"></a>继承的基础知识 (Visual Basic)

该`Inherits`语句用于根据称为*基类*的新类（称为*派生类*）声明新类。 派生类继承并可以扩展基类中定义的属性、方法、事件、字段和常量。 以下部分介绍继承的一些规则，以及可用于更改类继承或继承方式的修改器：

- 默认情况下，除非用 关键字标记，否则所有类都是`NotInheritable`可继承的。 类可以从项目中的其他类或项目引用的其他程序集中的类继承。

- 与允许多重继承的语言不同，Visual Basic 只允许在类中进行单个继承;也就是说，派生类只能有一个基类。 尽管类中不允许多次继承，但类可以实现多个接口，从而有效地实现相同的目的。

- 为了防止在基类中公开受限制项，派生类的访问类型必须等于或比其基类更具限制性。 `Public`例如，类不能继承 或`Friend``Private`类，并且`Friend`类不能继承类。 `Private`

## <a name="inheritance-modifiers"></a>继承修改器

Visual Basic 引入了以下类级语句和修改器来支持继承：

- `Inherits`语句 = 指定基类。

- `NotInheritable`修改器 = 防止程序员将类用作基类。

- `MustInherit`修改器 = 指定类仅用于基类。 不能直接创建`MustInherit`类的实例;因此，无法直接创建类的实例。它们只能创建为派生类的基类实例。 （其他编程语言（如C++和 C#）使用术语*抽象类*来描述此类。

## <a name="overriding-properties-and-methods-in-derived-classes"></a>派生类中的重写属性和方法

默认情况下，派生类继承其基类的属性和方法。 如果继承的属性或方法在派生类中的行为不同，则可以*重写*它。 也就是说，您可以在派生类中定义方法的新实现。 下列修饰符用于控制如何重写属性和方法：

- `Overridable`• 允许在派生类中重写类中的属性或方法。

- `Overrides`• 重写基`Overridable`类中定义的属性或方法。

- `NotOverridable`• 防止在继承类中重写属性或方法。 默认情况下，`Public`方法为`NotOverridable`。

- `MustOverride`• 要求派生类重写属性或方法。 使用`MustOverride`关键字时，方法定义仅包含`Sub`。 `Function`。 `Property` 不允许任何其他语句，特别是没有`End Sub`或`End Function`语句。 `MustOverride`方法必须在类中`MustInherit`声明。

假设您要定义要处理工资单的类。 您可以定义一个泛`Payroll`型类，其中包含计算`RunPayroll`典型星期的工资单的方法。 然后，您可以将用作`Payroll`更专业`BonusPayroll`类的基类，该类可用于分发员工奖金。

类`BonusPayroll`可以继承和重写基`PayEmployee``Payroll`类中定义的方法。

下面的示例定义基类`Payroll,`和派生类 ，`BonusPayroll`它重写继承的方法 。 `PayEmployee` 过程 ，`RunPayroll``Payroll`创建，然后将对象和`BonusPayroll`对象传递给一个函数 ，`Pay`执行两个对象`PayEmployee`的方法。

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>MyBase 关键字

关键字`MyBase`的作用类似于引用类当前实例的基类的对象变量。 `MyBase`通常用于访问派生类中重写或隐藏基类成员。 特别是，`MyBase.New`用于从派生类构造函数显式调用基类构造函数。

例如，假设您正在设计一个派生类，该类重写从基类继承的方法。 重写方法可以在基类中调用 方法并修改返回值，如以下代码片段所示：

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

下面的列表描述了对 使用`MyBase`的限制：

- `MyBase`指直接基类及其继承成员。 它不能用于访问`Private`类中的成员。

- `MyBase`是关键字，而不是真实对象。 `MyBase`不能分配给变量、传递给过程或用于`Is`比较。

- `MyBase`限定的方法不必在直接基类中定义;它可以在间接继承的基类中定义。 为了使 引用`MyBase`具有正确的编译，某些基类必须包含一个方法，匹配调用中显示的参数的名称和类型。

- 不能使用`MyBase`调用`MustOverride`基类方法。

- `MyBase`不能用来限定自己。 因此，以下代码无效：

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`不能在模块中使用。

- `MyBase`不能用于访问标记为`Friend`基类的基类成员，因为基类位于其他程序集中。

有关详细信息和另一个示例，请参阅[如何：访问派生类隐藏的变量](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。

## <a name="the-myclass-keyword"></a>MyClass 关键字

关键字`MyClass`的作用类似于对象变量，该变量引用最初实现的类的当前实例。 `MyClass`类似于`Me`，但每个方法和属性调用`MyClass`都被视为方法或属性[不是可重写的](../../../../visual-basic/language-reference/modifiers/notoverridable.md)。 因此，方法或属性不受派生类中重写的影响。

- `MyClass`是关键字，而不是真实对象。 `MyClass`不能分配给变量、传递给过程或用于`Is`比较。

- `MyClass`引用包含类及其继承成员。

- `MyClass`可用作成员的`Shared`限定符。

- `MyClass`不能在`Shared`方法内使用，但可以在实例方法内访问类的共享成员。

- `MyClass`不能在标准模块中使用。

- `MyClass`可用于限定在基类中定义且没有该类中提供的方法的实现的方法。 这种引用与`MyBase.`*方法*的含义相同。

下面的示例比较`Me`和`MyClass`。

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

`derivedClass`即使重写`testMethod`，`MyClass`中的`useMyClass`关键字将取消重写的效果，编译器解析对 基类版本的`testMethod`调用。

## <a name="see-also"></a>另请参阅

- [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
