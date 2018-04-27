---
title: 演练：用 COM 对象实现继承 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10c6bdf46e351b23705107da3b693531718cfd37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="78e92-102">演练：用 COM 对象实现继承 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78e92-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="78e92-103">您可以派生从 Visual Basic 类`Public`中 COM 对象，甚至那些在早期版本的 Visual Basic 中创建的类。</span><span class="sxs-lookup"><span data-stu-id="78e92-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="78e92-104">属性和方法从 COM 对象继承的类可以重写或只是作为属性重载，并可以重写任何其他基类方法，或将其重载。</span><span class="sxs-lookup"><span data-stu-id="78e92-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="78e92-105">具有不希望重新编译的现有类库时，从 COM 对象的继承非常有用。</span><span class="sxs-lookup"><span data-stu-id="78e92-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="78e92-106">以下过程演示如何使用 Visual Basic 6.0 中创建一个包含类的 COM 对象，然后将其用作基类。</span><span class="sxs-lookup"><span data-stu-id="78e92-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="78e92-107">若要生成本演练中使用的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="78e92-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="78e92-108">在 Visual Basic 6.0 中，打开新的 ActiveX DLL 项目。</span><span class="sxs-lookup"><span data-stu-id="78e92-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="78e92-109">一个名为项目`Project1`创建。</span><span class="sxs-lookup"><span data-stu-id="78e92-109">A project named `Project1` is created.</span></span> <span data-ttu-id="78e92-110">它具有一个名为类`Class1`。</span><span class="sxs-lookup"><span data-stu-id="78e92-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="78e92-111">在**项目资源管理器**，右键单击**Project1**，然后单击**Project1 属性**。</span><span class="sxs-lookup"><span data-stu-id="78e92-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="78e92-112">**项目属性**对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="78e92-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="78e92-113">上**常规**选项卡**项目属性**对话框框中，通过键入更改项目名称`ComObject1`中**项目名称**字段。</span><span class="sxs-lookup"><span data-stu-id="78e92-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="78e92-114">在**项目资源管理器**，右键单击`Class1`，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="78e92-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="78e92-115">**属性**显示窗口类。</span><span class="sxs-lookup"><span data-stu-id="78e92-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="78e92-116">更改`Name`属性`MathFunctions`。</span><span class="sxs-lookup"><span data-stu-id="78e92-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="78e92-117">在**项目资源管理器**，右键单击`MathFunctions`，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="78e92-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="78e92-118">**代码编辑器**显示。</span><span class="sxs-lookup"><span data-stu-id="78e92-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="78e92-119">添加一个本地变量以保存属性值：</span><span class="sxs-lookup"><span data-stu-id="78e92-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="78e92-120">将属性添加`Let`和属性`Get`属性过程：</span><span class="sxs-lookup"><span data-stu-id="78e92-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="78e92-121">添加一个函数：</span><span class="sxs-lookup"><span data-stu-id="78e92-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="78e92-122">创建并注册的 COM 对象，通过单击**使 ComObject1.dll**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="78e92-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78e92-123">尽管你可以公开为 COM 对象的 Visual basic 创建的类，但它不是真正的 COM 对象，并且不在本演练中使用。</span><span class="sxs-lookup"><span data-stu-id="78e92-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="78e92-124">有关详细信息，请参阅[在.NET Framework 应用程序的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="78e92-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="78e92-125">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="78e92-125">Interop Assemblies</span></span>  
 <span data-ttu-id="78e92-126">在以下过程中，你将创建一个互操作程序集，它将充当 （如 COM 对象） 的非托管的代码和托管的代码之间的桥梁[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="78e92-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses.</span></span> <span data-ttu-id="78e92-127">Visual Basic 创建的互操作程序集处理的许多细节，如使用 COM 对象的*互操作封送处理*，打包参数和返回值为等效的数据的过程类型标记为不将移到和从 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="78e92-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="78e92-128">在 Visual Basic 应用程序引用将指向互操作程序集，而不是实际的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="78e92-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="78e92-129">若要使用 Visual Basic 2005 和更高版本的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="78e92-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="78e92-130">打开一个新的 Visual Basic Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="78e92-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="78e92-131">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="78e92-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="78e92-132">将显示“添加引用”对话框。</span><span class="sxs-lookup"><span data-stu-id="78e92-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="78e92-133">上**COM**选项卡上，双击`ComObject1`中**组件名称**列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="78e92-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="78e92-134">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="78e92-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="78e92-135">随即出现“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="78e92-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="78e92-136">在**模板**窗格中，单击**类**。</span><span class="sxs-lookup"><span data-stu-id="78e92-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="78e92-137">默认文件名， `Class1.vb`，将出现在**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="78e92-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="78e92-138">将此字段更改为 MathClass.vb 和单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="78e92-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="78e92-139">这将创建一个名为类`MathClass`，并显示其代码。</span><span class="sxs-lookup"><span data-stu-id="78e92-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="78e92-140">将以下代码添加到顶部`MathClass`从 COM 类继承。</span><span class="sxs-lookup"><span data-stu-id="78e92-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  <span data-ttu-id="78e92-141">通过添加以下代码到重载的基类的公共方法`MathClass`:</span><span class="sxs-lookup"><span data-stu-id="78e92-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  <span data-ttu-id="78e92-142">通过添加以下代码来扩展继承的类`MathClass`:</span><span class="sxs-lookup"><span data-stu-id="78e92-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 <span data-ttu-id="78e92-143">此新类继承中的 COM 对象的基类的属性、 重载方法，并定义一个新方法来扩展类。</span><span class="sxs-lookup"><span data-stu-id="78e92-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="78e92-144">若要测试继承的类</span><span class="sxs-lookup"><span data-stu-id="78e92-144">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="78e92-145">启动窗体中，添加一个按钮，然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="78e92-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="78e92-146">在按钮的`Click`事件处理程序过程中，添加以下代码以创建的实例`MathClass`和调用的重载的方法：</span><span class="sxs-lookup"><span data-stu-id="78e92-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  <span data-ttu-id="78e92-147">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="78e92-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="78e92-148">单击窗体上的按钮时`AddNumbers`方法首先调用的`Short`数据类型的数字和 Visual Basic 选择相应的方法从基类。</span><span class="sxs-lookup"><span data-stu-id="78e92-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="78e92-149">第二次调用`AddNumbers`定向到中的重载方法`MathClass`。</span><span class="sxs-lookup"><span data-stu-id="78e92-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="78e92-150">第三个调用调用`SubtractNumbers`方法，扩展类。</span><span class="sxs-lookup"><span data-stu-id="78e92-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="78e92-151">设置中的基类的属性，并显示的值。</span><span class="sxs-lookup"><span data-stu-id="78e92-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="78e92-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="78e92-152">Next Steps</span></span>  
 <span data-ttu-id="78e92-153">你可能已经注意到，重载`AddNumbers`函数显示为具有相同的数据类型为继承自基类的 COM 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="78e92-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="78e92-154">这是因为自变量和参数的基类方法被定义为 16 位整数，在 Visual Basic 6.0 中，但它们公开为 16 位整数类型的`Short`更高版本的 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="78e92-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="78e92-155">新的函数可接受 32 位整数，并重载基类函数。</span><span class="sxs-lookup"><span data-stu-id="78e92-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="78e92-156">当使用 COM 对象，请确保验证参数的大小和数据类型。</span><span class="sxs-lookup"><span data-stu-id="78e92-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="78e92-157">例如，当使用接受 Visual Basic 6.0 集合对象作为参数的 COM 对象时，不能提供更高版本的 Visual Basic 中的集合。</span><span class="sxs-lookup"><span data-stu-id="78e92-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="78e92-158">属性和从 COM 类继承的方法可以重写，这意味着你可以声明的本地属性或替换属性的方法或继承自基类的 COM 的方法。</span><span class="sxs-lookup"><span data-stu-id="78e92-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="78e92-159">用于重写继承的 COM 属性的规则是类似的规则重写其他属性和方法有以下例外：</span><span class="sxs-lookup"><span data-stu-id="78e92-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="78e92-160">如果你重写任何属性或方法从 COM 类继承，则必须重写所有其他继承的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="78e92-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="78e92-161">使用的属性`ByRef`参数不能重写。</span><span class="sxs-lookup"><span data-stu-id="78e92-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e92-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="78e92-162">See Also</span></span>  
 [<span data-ttu-id="78e92-163">.NET Framework 应用程序中的 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="78e92-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="78e92-164">Inherits 语句</span><span class="sxs-lookup"><span data-stu-id="78e92-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="78e92-165">Short 数据类型</span><span class="sxs-lookup"><span data-stu-id="78e92-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
