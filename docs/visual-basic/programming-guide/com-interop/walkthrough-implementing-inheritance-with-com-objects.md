---
title: 演练：用 COM 对象实现继承
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: 209e1005b9f944bf4883e8406031fb17d4d60df1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347988"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>演练：用 COM 对象实现继承 (Visual Basic)

可以从 COM 对象 `Public` 类派生 Visual Basic 类，甚至可以从 Visual Basic 早期版本中创建的类派生。 可以重写或重载从 COM 对象继承的类的属性和方法，就像可以重写或重载任何其他基类的属性和方法一样。 当你有一个不想重新编译的现有类库时，COM 对象的继承很有用。

下面的过程演示如何使用 Visual Basic 6.0 创建一个包含类的 COM 对象，然后将其用作基类。

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>生成在本演练中使用的 COM 对象

1. 在 Visual Basic 6.0 中，打开一个新的 ActiveX DLL 项目。 创建名为 `Project1` 的项目。 它有一个名为 `Class1`的类。

2. 在 "**项目资源管理器**" 中，右键单击**Project1**，然后单击 " **Project1 属性**"。 随即显示 "**项目属性**" 对话框。

3. 在 "**项目属性**" 对话框的 "**常规**" 选项卡上，通过在 "**项目名称**" 字段中键入 `ComObject1` 来更改项目名称。

4. 在 "**项目资源管理器**" 中，右键单击 `Class1`，然后单击 "**属性**"。 将显示类的 "**属性**" 窗口。

5. 将 `Name` 属性更改为 `MathFunctions`。

6. 在 "**项目资源管理器**" 中，右键单击 `MathFunctions`，然后单击 "**查看代码**"。 将显示**代码编辑器**。

7. 添加本地变量来保存属性值：

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. 添加属性 `Let` 和属性 `Get` 属性过程：

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. 添加函数：

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. 通过在 "**文件**" 菜单上单击 "**生成 ComObject1** "，创建并注册 COM 对象。

    > [!NOTE]
    > 尽管还可以将使用 Visual Basic 创建的类公开为 COM 对象，但它不是真正的 COM 对象，因此不能在此演练中使用。 有关详细信息，请参阅[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。

## <a name="interop-assemblies"></a>互操作程序集

在下面的过程中，你将创建一个互操作程序集，该程序集充当非托管代码（如 COM 对象）和 Visual Studio 使用的托管代码之间的桥梁。 Visual Basic 创建的互操作程序集用于处理使用 COM 对象（如*互操作封送*处理）的许多详细信息，例如，将参数和返回值与 com 对象来回移动时，将参数和返回值打包成等效的数据类型。 Visual Basic 应用程序中的引用指向互操作程序集，而不是实际的 COM 对象。

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>将 COM 对象用于 Visual Basic 2005 及更高版本

1. 打开一个新的 Visual Basic Windows 应用程序项目。

2. 在“项目”菜单上，单击“添加引用”。

     将显示“添加引用”对话框。

3. 在 " **COM** " 选项卡上，双击 "**组件名称**" 列表中 `ComObject1`，然后单击 **"确定"** 。

4. 在 **“项目”** 菜单上，单击 **“添加新项”** 。

     随即出现“添加新项”对话框。

5. 在 "**模板**" 窗格中单击 "**类**"。

     默认文件名 `Class1.vb`会出现在 "**名称**" 字段中。 将此字段更改为 MathClass，然后单击 "**添加**"。 这将创建一个名为 `MathClass`的类，并显示其代码。

6. 将以下代码添加到 `MathClass` 的顶部，以便从 COM 类继承。

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. 通过将以下代码添加到 `MathClass`来重载基类的公共方法：

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. 通过将以下代码添加到 `MathClass`来扩展继承的类：

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

新类继承 COM 对象中基类的属性，重载方法，并定义新的方法来扩展类。

### <a name="to-test-the-inherited-class"></a>测试继承的类

1. 将按钮添加到启动窗体，然后双击它以查看其代码。

2. 在按钮的 `Click` 事件处理程序过程中，添加以下代码以创建 `MathClass` 的实例，并调用重载的方法：

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. 按 F5 运行项目。

单击窗体上的按钮时，将首先调用 `AddNumbers` 方法，并 `Short` 数据类型的数字，Visual Basic 从基类中选择适当的方法。 对 `AddNumbers` 的第二次调用将从 `MathClass`定向到重载方法。 第三个调用调用扩展类的 `SubtractNumbers` 方法。 基类中的属性已设置，并显示值。

## <a name="next-steps"></a>后续步骤

您可能已注意到重载的 `AddNumbers` 函数似乎与从 COM 对象的基类继承的方法具有相同的数据类型。 这是因为基类方法的参数和参数在 Visual Basic 6.0 中定义为16位整数，但在 Visual Basic 的更高版本中，它们将公开为类型 `Short` 的16位整数。 新函数接受32位整数，并重载基类函数。

使用 COM 对象时，请确保验证参数的大小和数据类型。 例如，使用接受 Visual Basic 6.0 集合对象作为参数的 COM 对象时，无法从 Visual Basic 的更高版本中提供集合。

可以重写从 COM 类继承的属性和方法，这意味着您可以声明一个本地属性或方法来替换继承自基类的属性或方法。 用于重写继承的 COM 属性的规则类似于重写其他属性和方法的规则，但以下情况例外：

- 如果重写从 COM 类继承的任何属性或方法，则必须重写所有其他继承的属性和方法。

- 不能重写使用 `ByRef` 参数的属性。

## <a name="see-also"></a>另请参阅

- [.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
