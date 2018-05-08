---
title: 演练：用 COM 对象实现继承 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: a1c1b7c247d3277c6614a4774395650c4c069c2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a>演练：用 COM 对象实现继承 (Visual Basic)
您可以派生从 Visual Basic 类`Public`中 COM 对象，甚至那些在早期版本的 Visual Basic 中创建的类。 属性和方法从 COM 对象继承的类可以重写或只是作为属性重载，并可以重写任何其他基类方法，或将其重载。 具有不希望重新编译的现有类库时，从 COM 对象的继承非常有用。  
  
 以下过程演示如何使用 Visual Basic 6.0 中创建一个包含类的 COM 对象，然后将其用作基类。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a>若要生成本演练中使用的 COM 对象  
  
1.  在 Visual Basic 6.0 中，打开新的 ActiveX DLL 项目。 一个名为项目`Project1`创建。 它具有一个名为类`Class1`。  
  
2.  在**项目资源管理器**，右键单击**Project1**，然后单击**Project1 属性**。 **项目属性**对话框随即显示。  
  
3.  上**常规**选项卡**项目属性**对话框框中，通过键入更改项目名称`ComObject1`中**项目名称**字段。  
  
4.  在**项目资源管理器**，右键单击`Class1`，然后单击**属性**。 **属性**显示窗口类。  
  
5.  更改`Name`属性`MathFunctions`。  
  
6.  在**项目资源管理器**，右键单击`MathFunctions`，然后单击**查看代码**。 **代码编辑器**显示。  
  
7.  添加一个本地变量以保存属性值：  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  将属性添加`Let`和属性`Get`属性过程：  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. 添加一个函数：  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. 创建并注册的 COM 对象，通过单击**使 ComObject1.dll**上**文件**菜单。  
  
    > [!NOTE]
    >  尽管你可以公开为 COM 对象的 Visual basic 创建的类，但它不是真正的 COM 对象，并且不在本演练中使用。 有关详细信息，请参阅[在.NET Framework 应用程序的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。  
  
## <a name="interop-assemblies"></a>互操作程序集  
 在下面的过程中，你将创建一个互操作的程序集，它作为非托管的代码 （如 COM 对象） 和 Visual Studio 将使用的托管的代码之间的桥梁。 Visual Basic 创建的互操作程序集处理的许多细节，如使用 COM 对象的*互操作封送处理*，打包参数和返回值为等效的数据的过程类型标记为不将移到和从 COM 对象。 在 Visual Basic 应用程序引用将指向互操作程序集，而不是实际的 COM 对象。  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a>若要使用 Visual Basic 2005 和更高版本的 COM 对象  
  
1.  打开一个新的 Visual Basic Windows 应用程序项目。  
  
2.  在“项目”菜单上，单击“添加引用”。  
  
     将显示“添加引用”对话框。  
  
3.  上**COM**选项卡上，双击`ComObject1`中**组件名称**列表，然后单击**确定**。  
  
4.  在 **“项目”** 菜单上，单击 **“添加新项”**。  
  
     随即出现“添加新项”对话框。  
  
5.  在**模板**窗格中，单击**类**。  
  
     默认文件名， `Class1.vb`，将出现在**名称**字段。 将此字段更改为 MathClass.vb 和单击**添加**。 这将创建一个名为类`MathClass`，并显示其代码。  
  
6.  将以下代码添加到顶部`MathClass`从 COM 类继承。  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  通过添加以下代码到重载的基类的公共方法`MathClass`:  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  通过添加以下代码来扩展继承的类`MathClass`:  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 此新类继承中的 COM 对象的基类的属性、 重载方法，并定义一个新方法来扩展类。  
  
#### <a name="to-test-the-inherited-class"></a>若要测试继承的类  
  
1.  启动窗体中，添加一个按钮，然后双击它以查看其代码。  
  
2.  在按钮的`Click`事件处理程序过程中，添加以下代码以创建的实例`MathClass`和调用的重载的方法：  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  按 F5 运行项目。  
  
 单击窗体上的按钮时`AddNumbers`方法首先调用的`Short`数据类型的数字和 Visual Basic 选择相应的方法从基类。 第二次调用`AddNumbers`定向到中的重载方法`MathClass`。 第三个调用调用`SubtractNumbers`方法，扩展类。 设置中的基类的属性，并显示的值。  
  
## <a name="next-steps"></a>后续步骤  
 你可能已经注意到，重载`AddNumbers`函数显示为具有相同的数据类型为继承自基类的 COM 对象的方法。 这是因为自变量和参数的基类方法被定义为 16 位整数，在 Visual Basic 6.0 中，但它们公开为 16 位整数类型的`Short`更高版本的 Visual Basic 中。 新的函数可接受 32 位整数，并重载基类函数。  
  
 当使用 COM 对象，请确保验证参数的大小和数据类型。 例如，当使用接受 Visual Basic 6.0 集合对象作为参数的 COM 对象时，不能提供更高版本的 Visual Basic 中的集合。  
  
 属性和从 COM 类继承的方法可以重写，这意味着你可以声明的本地属性或替换属性的方法或继承自基类的 COM 的方法。 用于重写继承的 COM 属性的规则是类似的规则重写其他属性和方法有以下例外：  
  
-   如果你重写任何属性或方法从 COM 类继承，则必须重写所有其他继承的属性和方法。  
  
-   使用的属性`ByRef`参数不能重写。  
  
## <a name="see-also"></a>请参阅  
 [.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)
