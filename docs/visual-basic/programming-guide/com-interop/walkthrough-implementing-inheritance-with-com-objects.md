---
title: "演练︰ 用 COM 对象 (Visual Basic 中) 实现继承 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0e816d1728678467d930de524b894d175f9b0c0a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="273b8-102">演练：用 COM 对象实现继承 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="273b8-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="273b8-103">您可以派生从 Visual Basic 类`Public`中 COM 对象，即使他们的早期版本中创建的类[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="273b8-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="273b8-104">属性和方法从 COM 对象继承的类可以重写或重载只是作为属性和方法的任何其他基类可以重写或重载。</span><span class="sxs-lookup"><span data-stu-id="273b8-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="273b8-105">从 COM 对象的继承具有不希望重新编译现有类库时很有帮助。</span><span class="sxs-lookup"><span data-stu-id="273b8-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="273b8-106">下面的过程演示如何使用 Visual Basic 6.0 中创建 COM 对象，其中包含一个类，并将其作为基类。</span><span class="sxs-lookup"><span data-stu-id="273b8-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="273b8-107">若要生成在本演练中使用的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="273b8-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="273b8-108">在 Visual Basic 6.0 中，打开一个新的 ActiveX DLL 项目。</span><span class="sxs-lookup"><span data-stu-id="273b8-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="273b8-109">一个名为项目`Project1`创建。</span><span class="sxs-lookup"><span data-stu-id="273b8-109">A project named `Project1` is created.</span></span> <span data-ttu-id="273b8-110">它具有一个名为类`Class1`。</span><span class="sxs-lookup"><span data-stu-id="273b8-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="273b8-111">在**项目资源管理器**，用鼠标右键单击**Project1**，然后单击**Project1 属性**。</span><span class="sxs-lookup"><span data-stu-id="273b8-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="273b8-112">**项目属性**中会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="273b8-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="273b8-113">在**常规**的选项卡上**项目属性**对话框框中，键入更改项目名称`ComObject1`中**项目名称**字段。</span><span class="sxs-lookup"><span data-stu-id="273b8-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="273b8-114">在**项目资源管理器**，用鼠标右键单击`Class1`，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="273b8-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="273b8-115">**属性**显示为类的窗口。</span><span class="sxs-lookup"><span data-stu-id="273b8-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="273b8-116">更改`Name`属性设置为`MathFunctions`。</span><span class="sxs-lookup"><span data-stu-id="273b8-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="273b8-117">在**项目资源管理器**，用鼠标右键单击`MathFunctions`，然后单击**查看代码**。</span><span class="sxs-lookup"><span data-stu-id="273b8-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="273b8-118">**代码编辑器**显示。</span><span class="sxs-lookup"><span data-stu-id="273b8-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="273b8-119">添加一个本地变量来保存属性值︰</span><span class="sxs-lookup"><span data-stu-id="273b8-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="273b8-120">将属性添加`Let`和属性`Get`属性过程︰</span><span class="sxs-lookup"><span data-stu-id="273b8-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="273b8-121">添加一个函数︰</span><span class="sxs-lookup"><span data-stu-id="273b8-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="273b8-122">创建和注册的 COM 对象，通过单击**使 ComObject1.dll**上**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="273b8-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="273b8-123">尽管您还可以公开与所创建的类[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]作为 COM 对象，它不是真正的 COM 对象，不能在本演练中使用。</span><span class="sxs-lookup"><span data-stu-id="273b8-123">Although you can also expose a class created with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="273b8-124">有关详细信息，请参阅[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="273b8-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="273b8-125">互操作程序集</span><span class="sxs-lookup"><span data-stu-id="273b8-125">Interop Assemblies</span></span>  
 <span data-ttu-id="273b8-126">在以下过程中，您将创建一个互操作程序集，它将作为非托管的代码 （如 COM 对象） 和托管的代码之间的桥梁[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="273b8-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] uses.</span></span> <span data-ttu-id="273b8-127">互操作程序集，[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]创建句柄对象的许多使用 COM 的详细信息，如*互操作封送处理*，包装参数和返回值转换为等效的数据的进程类型标记为它们移动到和从 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="273b8-127">The interop assembly that [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="273b8-128">中的引用[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]互操作程序集，而不是实际的 COM 对象的应用程序指向。</span><span class="sxs-lookup"><span data-stu-id="273b8-128">The reference in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="273b8-129">若要使用 Visual Basic 2005 和更高版本的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="273b8-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="273b8-130">打开一个新[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="273b8-130">Open a new [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="273b8-131">在**项目**菜单上，单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="273b8-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="273b8-132">**添加引用**中会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="273b8-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="273b8-133">在**COM**选项卡上，双击`ComObject1`中**组件名称**列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="273b8-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="273b8-134">在 **“项目”** 菜单上，单击 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="273b8-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="273b8-135">**添加新项**中会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="273b8-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="273b8-136">在**模板**窗格中，单击**类**。</span><span class="sxs-lookup"><span data-stu-id="273b8-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="273b8-137">默认文件名， `Class1.vb`，将出现在**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="273b8-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="273b8-138">将此字段更改为 MathClass.vb，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="273b8-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="273b8-139">这将创建一个名为类`MathClass`，并显示其代码。</span><span class="sxs-lookup"><span data-stu-id="273b8-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="273b8-140">将以下代码添加到顶部`MathClass`从 COM 类继承。</span><span class="sxs-lookup"><span data-stu-id="273b8-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     <span data-ttu-id="273b8-141">[!code-vb[VbVbalrInterop #&31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="273b8-141">[!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span></span>  
  
7.  <span data-ttu-id="273b8-142">通过添加以下代码到重载的基类的公共方法`MathClass`:</span><span class="sxs-lookup"><span data-stu-id="273b8-142">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="273b8-143">[!code-vb[VbVbalrInterop #&32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="273b8-143">[!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span></span>  
  
8.  <span data-ttu-id="273b8-144">通过添加下面的代码来扩展继承的类`MathClass`:</span><span class="sxs-lookup"><span data-stu-id="273b8-144">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="273b8-145">[!code-vb[VbVbalrInterop 第&33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="273b8-145">[!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span></span>  
  
 <span data-ttu-id="273b8-146">新类继承的属性中的 COM 对象的基类，重载方法，并定义要扩展类的新方法。</span><span class="sxs-lookup"><span data-stu-id="273b8-146">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="273b8-147">若要测试继承的类</span><span class="sxs-lookup"><span data-stu-id="273b8-147">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="273b8-148">向启动窗体中，添加一个按钮，然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="273b8-148">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="273b8-149">在按钮的`Click`事件处理程序，添加以下代码以创建的实例`MathClass`并调用重载的方法︰</span><span class="sxs-lookup"><span data-stu-id="273b8-149">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     <span data-ttu-id="273b8-150">[!code-vb[VbVbalrInterop #&34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="273b8-150">[!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span></span>  
  
3.  <span data-ttu-id="273b8-151">通过按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="273b8-151">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="273b8-152">当您单击在表单上，按钮时`AddNumbers`方法首先调用的`Short`数据类型的数字，和[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]选择适当的方法从基类。</span><span class="sxs-lookup"><span data-stu-id="273b8-152">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chooses the appropriate method from the base class.</span></span> <span data-ttu-id="273b8-153">第二次调用`AddNumbers`定向到的重载方法`MathClass`。</span><span class="sxs-lookup"><span data-stu-id="273b8-153">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="273b8-154">第三个调用调用`SubtractNumbers`方法，扩展类。</span><span class="sxs-lookup"><span data-stu-id="273b8-154">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="273b8-155">设置了基类中的属性，并且显示的值。</span><span class="sxs-lookup"><span data-stu-id="273b8-155">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="273b8-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="273b8-156">Next Steps</span></span>  
 <span data-ttu-id="273b8-157">您可能已经注意到，重载`AddNumbers`函数起来都具有相同的数据类型为继承自基类的 COM 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="273b8-157">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="273b8-158">这是因为参数和参数的基类方法被定义为 16 位整数，在 Visual Basic 6.0 中，但它们公开为 16 位整数类型的`Short`更高版本的 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="273b8-158">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="273b8-159">新函数接受 32 位整数，并重载基类函数。</span><span class="sxs-lookup"><span data-stu-id="273b8-159">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="273b8-160">当使用 COM 对象，请确保验证参数的大小和数据类型。</span><span class="sxs-lookup"><span data-stu-id="273b8-160">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="273b8-161">例如，当使用接受 Visual Basic 6.0 集合对象作为参数的 COM 对象时，不能提供更高版本的 Visual Basic 中的集合。</span><span class="sxs-lookup"><span data-stu-id="273b8-161">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="273b8-162">属性和从 COM 类继承的方法可以重写，意味着您可以声明本地属性或方法来代替一个属性或方法继承自基类的 COM 类。</span><span class="sxs-lookup"><span data-stu-id="273b8-162">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="273b8-163">重写继承的 COM 属性的规则是相似的规则重写其他属性和方法有以下例外︰</span><span class="sxs-lookup"><span data-stu-id="273b8-163">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="273b8-164">如果重写任何属性或方法从 COM 类继承时，必须重写所有其他继承的属性和方法。</span><span class="sxs-lookup"><span data-stu-id="273b8-164">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="273b8-165">使用属性`ByRef`参数不能重写。</span><span class="sxs-lookup"><span data-stu-id="273b8-165">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="273b8-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="273b8-166">See Also</span></span>  
 <span data-ttu-id="273b8-167">[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="273b8-167">[COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="273b8-168"> [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="273b8-168"> [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="273b8-169"> [Short 数据类型](../../../visual-basic/language-reference/data-types/short-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="273b8-169"> [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)</span></span>
