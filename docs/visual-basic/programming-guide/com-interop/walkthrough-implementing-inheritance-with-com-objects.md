---
title: 演练：实现与 COM 对象的继承 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: f632df919417c04701727be3e99eb2bf3f6ff1f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627039"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="c193a-102">演练：实现与 COM 对象的继承 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c193a-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="c193a-103">可以从 COM 对象中的`Public`类派生 Visual Basic 类, 甚至可以从 Visual Basic 早期版本中创建的类派生。</span><span class="sxs-lookup"><span data-stu-id="c193a-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="c193a-104">可以重写或重载从 COM 对象继承的类的属性和方法, 就像可以重写或重载任何其他基类的属性和方法一样。</span><span class="sxs-lookup"><span data-stu-id="c193a-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="c193a-105">当你有一个不想重新编译的现有类库时, COM 对象的继承很有用。</span><span class="sxs-lookup"><span data-stu-id="c193a-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="c193a-106">下面的过程演示如何使用 Visual Basic 6.0 创建一个包含类的 COM 对象, 然后将其用作基类。</span><span class="sxs-lookup"><span data-stu-id="c193a-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="c193a-107">生成在本演练中使用的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="c193a-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="c193a-108">在 Visual Basic 6.0 中, 打开一个新的 ActiveX DLL 项目。</span><span class="sxs-lookup"><span data-stu-id="c193a-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="c193a-109">创建名`Project1`为的项目。</span><span class="sxs-lookup"><span data-stu-id="c193a-109">A project named `Project1` is created.</span></span> <span data-ttu-id="c193a-110">它有一个名为`Class1`的类。</span><span class="sxs-lookup"><span data-stu-id="c193a-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="c193a-111">在 "**项目资源管理器**" 中, 右键单击**Project1**, 然后单击 " **Project1 属性**"。</span><span class="sxs-lookup"><span data-stu-id="c193a-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="c193a-112">随即显示 "**项目属性**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="c193a-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="c193a-113">在 "**项目属性**" 对话框的 "**常规**" 选项卡上, 通过在 " `ComObject1` **项目名称**" 字段中键入来更改项目名称。</span><span class="sxs-lookup"><span data-stu-id="c193a-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="c193a-114">在 "**项目资源管理器**" 中`Class1`, 右键单击, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c193a-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="c193a-115">将显示类的 "**属性**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="c193a-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="c193a-116">将属性更改为`MathFunctions`。 `Name`</span><span class="sxs-lookup"><span data-stu-id="c193a-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="c193a-117">在 "**项目资源管理器**" 中`MathFunctions`, 右键单击, 然后单击 "**查看代码**"。</span><span class="sxs-lookup"><span data-stu-id="c193a-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="c193a-118">将显示**代码编辑器**。</span><span class="sxs-lookup"><span data-stu-id="c193a-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="c193a-119">添加本地变量来保存属性值:</span><span class="sxs-lookup"><span data-stu-id="c193a-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="c193a-120">添加属性`Let`和属性`Get`过程:</span><span class="sxs-lookup"><span data-stu-id="c193a-120">Add Property `Let` and Property `Get` property procedures:</span></span>

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

9. <span data-ttu-id="c193a-121">添加函数:</span><span class="sxs-lookup"><span data-stu-id="c193a-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="c193a-122">通过在 "**文件**" 菜单上单击 "**生成 ComObject1** ", 创建并注册 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="c193a-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c193a-123">尽管还可以将使用 Visual Basic 创建的类公开为 COM 对象, 但它不是真正的 COM 对象, 因此不能在此演练中使用。</span><span class="sxs-lookup"><span data-stu-id="c193a-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="c193a-124">有关详细信息, 请参阅[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="c193a-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="c193a-125">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="c193a-125">Interop Assemblies</span></span>

<span data-ttu-id="c193a-126">在下面的过程中, 你将创建一个互操作程序集, 该程序集充当非托管代码 (如 COM 对象) 和 Visual Studio 使用的托管代码之间的桥梁。</span><span class="sxs-lookup"><span data-stu-id="c193a-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="c193a-127">Visual Basic 创建的互操作程序集用于处理使用 COM 对象 (如*互操作封送*处理) 的许多详细信息, 例如, 将参数和返回值与 com 对象来回移动时, 将参数和返回值打包成等效的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c193a-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="c193a-128">Visual Basic 应用程序中的引用指向互操作程序集, 而不是实际的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="c193a-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="c193a-129">将 COM 对象用于 Visual Basic 2005 及更高版本</span><span class="sxs-lookup"><span data-stu-id="c193a-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="c193a-130">打开一个新的 Visual Basic Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="c193a-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="c193a-131">在“项目”菜单上，单击“添加引用”   。</span><span class="sxs-lookup"><span data-stu-id="c193a-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="c193a-132">将显示“添加引用”对话框  。</span><span class="sxs-lookup"><span data-stu-id="c193a-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="c193a-133">在 " **COM** " 选项卡上, `ComObject1`在 "**组件名称**" 列表中双击, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="c193a-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="c193a-134">在 **“项目”** 菜单上，单击 **“添加新项”** 。</span><span class="sxs-lookup"><span data-stu-id="c193a-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="c193a-135">随即出现“添加新项”  对话框。</span><span class="sxs-lookup"><span data-stu-id="c193a-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="c193a-136">在 "**模板**" 窗格中单击 "**类**"。</span><span class="sxs-lookup"><span data-stu-id="c193a-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="c193a-137">默认文件名称`Class1.vb`将显示在 "**名称**" 字段中。</span><span class="sxs-lookup"><span data-stu-id="c193a-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="c193a-138">将此字段更改为 MathClass, 然后单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="c193a-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="c193a-139">这将创建一个名`MathClass`为的类, 并显示其代码。</span><span class="sxs-lookup"><span data-stu-id="c193a-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="c193a-140">向顶部`MathClass`添加以下代码, 以从 COM 类继承。</span><span class="sxs-lookup"><span data-stu-id="c193a-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="c193a-141">通过将以下代码添加到来`MathClass`重载基类的公共方法:</span><span class="sxs-lookup"><span data-stu-id="c193a-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="c193a-142">通过将以下代码添加到来`MathClass`扩展继承类:</span><span class="sxs-lookup"><span data-stu-id="c193a-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="c193a-143">新类继承 COM 对象中基类的属性, 重载方法, 并定义新的方法来扩展类。</span><span class="sxs-lookup"><span data-stu-id="c193a-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="c193a-144">测试继承的类</span><span class="sxs-lookup"><span data-stu-id="c193a-144">To test the inherited class</span></span>

1. <span data-ttu-id="c193a-145">将按钮添加到启动窗体, 然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="c193a-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="c193a-146">在按钮的`Click`事件处理程序过程中, 添加以下代码以创建的`MathClass`实例并调用重载的方法:</span><span class="sxs-lookup"><span data-stu-id="c193a-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="c193a-147">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="c193a-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="c193a-148">当单击窗体上的按钮时, 将`AddNumbers`首先`Short`调用该方法的数据类型, 然后 Visual Basic 从基类中选择适当的方法。</span><span class="sxs-lookup"><span data-stu-id="c193a-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="c193a-149">对`AddNumbers`的第二次调用将定向到中`MathClass`的重载方法。</span><span class="sxs-lookup"><span data-stu-id="c193a-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="c193a-150">第三个调用调用`SubtractNumbers`扩展类的方法。</span><span class="sxs-lookup"><span data-stu-id="c193a-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="c193a-151">基类中的属性已设置, 并显示值。</span><span class="sxs-lookup"><span data-stu-id="c193a-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c193a-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c193a-152">Next Steps</span></span>

<span data-ttu-id="c193a-153">您可能已注意到, 重载`AddNumbers`函数似乎与从 COM 对象的基类继承的方法具有相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="c193a-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="c193a-154">这是因为基类方法的参数和参数在 Visual Basic 6.0 中定义为16位整数, 但在 Visual Basic 的更高版本中, 它们将公开为类型`Short`的16位整数。</span><span class="sxs-lookup"><span data-stu-id="c193a-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="c193a-155">新函数接受32位整数, 并重载基类函数。</span><span class="sxs-lookup"><span data-stu-id="c193a-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="c193a-156">使用 COM 对象时, 请确保验证参数的大小和数据类型。</span><span class="sxs-lookup"><span data-stu-id="c193a-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="c193a-157">例如, 使用接受 Visual Basic 6.0 集合对象作为参数的 COM 对象时, 无法从 Visual Basic 的更高版本中提供集合。</span><span class="sxs-lookup"><span data-stu-id="c193a-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="c193a-158">可以重写从 COM 类继承的属性和方法, 这意味着您可以声明一个本地属性或方法来替换继承自基类的属性或方法。</span><span class="sxs-lookup"><span data-stu-id="c193a-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="c193a-159">用于重写继承的 COM 属性的规则类似于重写其他属性和方法的规则, 但以下情况例外:</span><span class="sxs-lookup"><span data-stu-id="c193a-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="c193a-160">如果重写从 COM 类继承的任何属性或方法, 则必须重写所有其他继承的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="c193a-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="c193a-161">不能重`ByRef`写使用参数的属性。</span><span class="sxs-lookup"><span data-stu-id="c193a-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="c193a-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="c193a-162">See also</span></span>

- [<span data-ttu-id="c193a-163">.NET Framework 应用程序中的 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="c193a-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="c193a-164">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="c193a-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="c193a-165">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="c193a-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
