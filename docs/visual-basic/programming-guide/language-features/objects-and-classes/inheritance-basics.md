---
title: 继承的基础知识 (Visual Basic)
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
ms.openlocfilehash: 9225e5fd9fa35ae06414018a109f66515f99363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655184"
---
# <a name="inheritance-basics-visual-basic"></a>继承的基础知识 (Visual Basic)
`Inherits`语句用于声明新类，称为*派生类*基于现有类，称为*基类*。 派生的类继承，并且可以扩展属性、 方法、 事件、 字段和基类中定义的常量。 以下部分介绍了一些继承的规则并可以使用要更改的方式类修饰符继承或继承：  
  
-   默认情况下，所有类都是可继承，除非标记有`NotInheritable`关键字。 从你的项目中的其他类或从你的项目引用其他程序集中的类，类可以继承。  
  
-   不同于允许多个继承的语言，Visual Basic 只允许单个中继承类;即，派生的类只能有一个基类。 虽然类中不允许多个继承，类可以实现多个接口，可以有效地实现相同目的。  
  
-   若要防止公开基类中的受限制的项，必须等于或限制性强于其基本类派生的类的访问类型。 例如，`Public`类不能继承`Friend`或`Private`类，和一个`Friend`类不能继承`Private`类。  
  
## <a name="inheritance-modifiers"></a>继承修饰符  
 Visual Basic 引入了以下类级语句和修饰符以支持继承：  
  
-   `Inherits` 语句-指定的基类。  
  
-   `NotInheritable` 修饰符 — 使程序员使用类用作基类。  
  
-   `MustInherit` 修饰符-指定类旨在用作仅基类。 实例`MustInherit`类不能直接创建; 它们只能创建的派生类作为基类的类实例。 (其他编程语言，例如 c + + 和 C# 中，使用术语*抽象类*来描述这样的类。)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>重写属性和派生类中的方法  
 默认情况下，派生的类从其基类中继承属性和方法。 如果继承的属性或方法具有不同的行为在派生类中它可以是*中被重写*。 也就是说，你可以在派生类中定义方法的新实现。 下列修饰符用于控制如何重写属性和方法：  
  
-   `Overridable` -在派生类中重写的类中，允许的属性或方法。  
  
-   `Overrides` -重写`Overridable`属性或在基类中定义的方法。  
  
-   `NotOverridable` -防止属性或方法被重写在继承类。 默认情况下，`Public`方法`NotOverridable`。  
  
-   `MustOverride` -需要派生的类重写的属性或方法。 当`MustOverride`使用关键字、 方法定义组成仅`Sub`， `Function`，或`Property`语句。 允许不存在其他语句，并且具体是有没有`End Sub`或`End Function`语句。 `MustOverride` 必须在声明方法`MustInherit`类。  
  
 假设你想要定义类以处理工资单。 你可以定义一个泛型`Payroll`类，该类包含`RunPayroll`典型周计算工资单的方法。 然后可以使用`Payroll`作为更专用的基类`BonusPayroll`类，该类分发雇员奖金时无法使用。  
  
 `BonusPayroll`类可以继承并重写，`PayEmployee`基类中定义的方法`Payroll`类。  
  
 下面的示例定义的基类，`Payroll,`和派生的类， `BonusPayroll`，这会重写继承的方法， `PayEmployee`。 一个过程中， `RunPayroll`、 创建并随后将传递`Payroll`对象和一个`BonusPayroll`、 指向函数的对象`Pay`，执行`PayEmployee`这两个对象的方法。  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>MyBase 关键字  
 `MyBase`关键字的行为类似一个类的当前实例的基类引用的对象变量。 `MyBase` 经常用于访问被重写或隐藏在派生类的基类成员。 具体而言，`MyBase.New`用于从派生的类构造函数中显式调用基类构造函数。  
  
 例如，假设您正在设计一个重写从基类继承的方法的派生的类。 重写的方法可以调用基类中的方法，并修改返回的值，如下面的代码段中所示：  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 以下列表描述对使用的限制`MyBase`:  
  
-   `MyBase` 指即时基类和继承的成员。 它不能访问`Private`中类的成员。  
  
-   `MyBase` 是关键字，而不是真实对象。 `MyBase` 不能分配给一个变量，传递给过程，或用于`Is`比较。  
  
-   方法的`MyBase`限定不必定义中即时基类; 它改为定义中的间接继承的基类。 为了使限定的引用`MyBase`正确编译，一些基类必须包含匹配的名称和类型的调用中出现的参数的方法。  
  
-   不能使用`MyBase`调用`MustOverride`基类方法。  
  
-   `MyBase` 不能用于限定本身。 因此，下面的代码不是有效的：  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` 不能在模块中使用。  
  
-   `MyBase` 不能用于访问基类成员标记为`Friend`基类是否在其他程序集中。  
  
 有关详细信息和另一个示例，请参阅[如何： 访问被派生类变量隐藏](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)。  
  
## <a name="the-myclass-keyword"></a>MyClass 关键字  
 `MyClass`关键字的行为方式类似于最初实现的类的当前实例是指的对象变量。 `MyClass` 类似于`Me`，但每个方法和属性调用上`MyClass`视为如同的方法或属性是[NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)。 因此，该方法或属性不受在派生类中重写。  
  
-   `MyClass` 是关键字，而不是真实对象。 `MyClass` 不能分配给一个变量，传递给过程，或用于`Is`比较。  
  
-   `MyClass` 指包含的类和其继承的成员。  
  
-   `MyClass` 可以用作限定符`Shared`成员。  
  
-   `MyClass` 不能用在`Shared`方法，但是可以在实例方法中用来访问共享的成员的类。  
  
-   `MyClass` 不能在标准模块中使用。  
  
-   `MyClass` 可以用于限定基类中定义并具有在该类中提供的方法没有实现的方法。 这种引用具有的相同含义与`MyBase.`*方法*。  
  
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
  
 即使`derivedClass`重写`testMethod`、`MyClass`中的关键字`useMyClass`使重写，和编译器解析无效的基类版本调用`testMethod`。  
  
## <a name="see-also"></a>请参阅  
 [Inherits 语句](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Me、My、MyBase 和 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
