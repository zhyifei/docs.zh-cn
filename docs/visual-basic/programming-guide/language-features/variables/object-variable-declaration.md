---
title: "对象变量声明 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cdca188d778e9884f918d97eba492a29c64af826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-declaration-visual-basic"></a><span data-ttu-id="dbd2a-102">对象变量声明 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbd2a-102">Object Variable Declaration (Visual Basic)</span></span>
<span data-ttu-id="dbd2a-103">你可以使用正常的声明语句来声明对象变量。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-103">You use a normal declaration statement to declare an object variable.</span></span> <span data-ttu-id="dbd2a-104">对于数据类型中，你指定`Object`(即， [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)) 或更具体的类是要创建对象。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-104">For the data type, you specify either `Object` (that is, the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)) or a more specific class from which the object is to be created.</span></span>  
  
 <span data-ttu-id="dbd2a-105">声明一个变量，作为`Object`等同于其声明为<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-105">Declaring a variable as `Object` is the same as declaring it as <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="dbd2a-106">在声明具有特定对象类的变量时，它可以访问所有方法和属性公开的类和它所继承的类。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-106">When you declare a variable with a specific object class, it can access all the methods and properties exposed by that class and the classes from which it inherits.</span></span> <span data-ttu-id="dbd2a-107">如果声明的变量进行<xref:System.Object>，它可以访问的成员<xref:System.Object>类，除非你打开`Option Strict Off`以允许后期绑定。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-107">If you declare the variable with <xref:System.Object>, it can access only the members of the <xref:System.Object> class, unless you turn `Option Strict Off` to allow late binding.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="dbd2a-108">声明语法</span><span class="sxs-lookup"><span data-stu-id="dbd2a-108">Declaration Syntax</span></span>  
 <span data-ttu-id="dbd2a-109">使用以下语法来声明对象变量：</span><span class="sxs-lookup"><span data-stu-id="dbd2a-109">Use the following syntax to declare an object variable:</span></span>  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 <span data-ttu-id="dbd2a-110">你还可以指定[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)， `Protected Friend`，[私有](../../../../visual-basic/language-reference/modifiers/private.md)，[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，或[静态](../../../../visual-basic/language-reference/modifiers/static.md)声明中。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-110">You can also specify [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), or [Static](../../../../visual-basic/language-reference/modifiers/static.md) in the declaration.</span></span> <span data-ttu-id="dbd2a-111">下面的示例声明为有效值：</span><span class="sxs-lookup"><span data-stu-id="dbd2a-111">The following example declarations are valid:</span></span>  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a><span data-ttu-id="dbd2a-112">后期绑定和早期绑定</span><span class="sxs-lookup"><span data-stu-id="dbd2a-112">Late Binding and Early Binding</span></span>  
 <span data-ttu-id="dbd2a-113">有时，你的代码运行时，才，也是未知的特定类。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-113">Sometimes the specific class is unknown until your code runs.</span></span> <span data-ttu-id="dbd2a-114">在这种情况下，您必须声明对象变量`Object`数据类型。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-114">In this case, you must declare the object variable with the `Object` data type.</span></span> <span data-ttu-id="dbd2a-115">这将创建常规指向任何类型的引用对象，并在运行时分配的特定类。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-115">This creates a general reference to any type of object, and the specific class is assigned at run time.</span></span> <span data-ttu-id="dbd2a-116">这称为*后期绑定*。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-116">This is called *late binding*.</span></span> <span data-ttu-id="dbd2a-117">后期绑定需要更多的执行时间。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-117">Late binding requires additional execution time.</span></span> <span data-ttu-id="dbd2a-118">它还会限制你的代码的方法和属性的最近已将分配给它的类。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-118">It also limits your code to the methods and properties of the class you have most recently assigned to it.</span></span> <span data-ttu-id="dbd2a-119">如果你的代码尝试访问不同类的成员，这可能导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-119">This can cause run-time errors if your code attempts to access members of a different class.</span></span>  
  
 <span data-ttu-id="dbd2a-120">当在编译时知道特定的类时，应将声明为该类的对象变量。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-120">When you know the specific class at compile time, you should declare the object variable to be of that class.</span></span> <span data-ttu-id="dbd2a-121">这称为*早期绑定*。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-121">This is called *early binding*.</span></span> <span data-ttu-id="dbd2a-122">早期绑定会改进性能，并可保证您对所有的方法和属性的特定类的代码访问权限。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-122">Early binding improves performance and guarantees your code access to all the methods and properties of the specific class.</span></span> <span data-ttu-id="dbd2a-123">在前面的示例声明中，如果变量`objA`使用仅类的对象<xref:System.Windows.Forms.Label?displayProperty=nameWithType>，应指定`As System.Windows.Forms.Label`其声明中。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-123">In the preceding example declarations, if variable `objA` uses only objects of class <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, you should specify `As System.Windows.Forms.Label` in its declaration.</span></span>  
  
### <a name="advantages-of-early-binding"></a><span data-ttu-id="dbd2a-124">早期绑定的优点</span><span class="sxs-lookup"><span data-stu-id="dbd2a-124">Advantages of Early Binding</span></span>  
 <span data-ttu-id="dbd2a-125">声明为特定类的对象变量为你提供几个优点：</span><span class="sxs-lookup"><span data-stu-id="dbd2a-125">Declaring an object variable as a specific class gives you several advantages:</span></span>  
  
-   <span data-ttu-id="dbd2a-126">自动类型检查</span><span class="sxs-lookup"><span data-stu-id="dbd2a-126">Automatic type checking</span></span>  
  
-   <span data-ttu-id="dbd2a-127">保证到特定的类的所有成员的访问</span><span class="sxs-lookup"><span data-stu-id="dbd2a-127">Guaranteed access to all members of the specific class</span></span>  
  
-   <span data-ttu-id="dbd2a-128">Microsoft IntelliSense 支持在代码编辑器</span><span class="sxs-lookup"><span data-stu-id="dbd2a-128">Microsoft IntelliSense support in the Code Editor</span></span>  
  
-   <span data-ttu-id="dbd2a-129">提高的代码的可读性</span><span class="sxs-lookup"><span data-stu-id="dbd2a-129">Improved readability of your code</span></span>  
  
-   <span data-ttu-id="dbd2a-130">在代码中减少错误</span><span class="sxs-lookup"><span data-stu-id="dbd2a-130">Fewer errors in your code</span></span>  
  
-   <span data-ttu-id="dbd2a-131">处捕获的错误编译时间而不是运行时</span><span class="sxs-lookup"><span data-stu-id="dbd2a-131">Errors caught at compile time rather than run time</span></span>  
  
-   <span data-ttu-id="dbd2a-132">代码执行速度更快</span><span class="sxs-lookup"><span data-stu-id="dbd2a-132">Faster code execution</span></span>  
  
## <a name="access-to-object-variable-members"></a><span data-ttu-id="dbd2a-133">对象变量成员的访问权限</span><span class="sxs-lookup"><span data-stu-id="dbd2a-133">Access to Object Variable Members</span></span>  
 <span data-ttu-id="dbd2a-134">当`Option Strict`处于打开状态`On`，仅的方法和属性与其声明的类，可以访问的对象变量。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-134">When `Option Strict` is turned `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="dbd2a-135">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-135">The following example illustrates this.</span></span>  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 <span data-ttu-id="dbd2a-136">在此示例中， `p` 仅可使用 <xref:System.Object> 类的成员，这不包括 `Left` 属性。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-136">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="dbd2a-137">另一方面， `q` 已声明为 <xref:System.Windows.Forms.Label>类型，因此它可以使用 <xref:System.Windows.Forms.Label> 命名空间中 <xref:System.Windows.Forms> 类的所有方法和属性。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-137">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="flexibility-of-object-variables"></a><span data-ttu-id="dbd2a-138">对象变量的灵活性</span><span class="sxs-lookup"><span data-stu-id="dbd2a-138">Flexibility of Object Variables</span></span>  
 <span data-ttu-id="dbd2a-139">在使用继承层次结构中的对象，可以用来声明对象变量的类的选择。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-139">When working with objects in an inheritance hierarchy, you have a choice of which class to use for declaring your object variables.</span></span> <span data-ttu-id="dbd2a-140">在进行选择时，必须综合考虑针对的类成员访问的对象赋值的灵活性。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-140">In making this choice, you must balance flexibility of object assignment against access to members of a class.</span></span> <span data-ttu-id="dbd2a-141">例如，考虑继承层次结构会导致<xref:System.Windows.Forms.Form?displayProperty=nameWithType>类：</span><span class="sxs-lookup"><span data-stu-id="dbd2a-141">For example, consider the inheritance hierarchy that leads to the <xref:System.Windows.Forms.Form?displayProperty=nameWithType> class:</span></span>  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 <span data-ttu-id="dbd2a-142">假设你的应用程序定义一个名为的窗体类`specialForm`，它继承自类<xref:System.Windows.Forms.Form>。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-142">Suppose your application defines a form class called `specialForm`, which inherits from class <xref:System.Windows.Forms.Form>.</span></span> <span data-ttu-id="dbd2a-143">你可以声明专门引用的对象变量`specialForm`，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-143">You can declare an object variable that refers specifically to `specialForm`, as the following example shows.</span></span>  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 <span data-ttu-id="dbd2a-144">在前面的示例声明限制变量`nextForm`类的对象到`specialForm`，而且也使所有的方法和属性`specialForm`供`nextForm`，以及从其的所有类的所有成员`specialForm`继承。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-144">The declaration in the preceding example limits the variable `nextForm` to objects of class `specialForm`, but it also makes all the methods and properties of `specialForm` available to `nextForm`, as well as all the members of all the classes from which `specialForm` inherits.</span></span>  
  
 <span data-ttu-id="dbd2a-145">你可以通过声明的类型，才能使对象变量更多常规<xref:System.Windows.Forms.Form>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-145">You can make an object variable more general by declaring it to be of type <xref:System.Windows.Forms.Form>, as the following example shows.</span></span>  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 <span data-ttu-id="dbd2a-146">在前面的示例声明，您可以分配到应用程序中的任何窗体`anyForm`。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-146">The declaration in the preceding example lets you assign any form in your application to `anyForm`.</span></span> <span data-ttu-id="dbd2a-147">但是，尽管`anyForm`可以访问的类的所有成员<xref:System.Windows.Forms.Form>，它不能使用任何其他方法或属性，如为特定窗体定义`specialForm`。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-147">However, although `anyForm` can access all the members of class <xref:System.Windows.Forms.Form>, it cannot use any of the additional methods or properties defined for specific forms such as `specialForm`.</span></span>  
  
 <span data-ttu-id="dbd2a-148">基类的所有成员都均可用于派生的类，但派生类的其他成员与基的类不可用。</span><span class="sxs-lookup"><span data-stu-id="dbd2a-148">All the members of a base class are available to derived classes, but the additional members of a derived class are unavailable to the base class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd2a-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbd2a-149">See Also</span></span>  
 [<span data-ttu-id="dbd2a-150">对象变量</span><span class="sxs-lookup"><span data-stu-id="dbd2a-150">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="dbd2a-151">对象变量赋值</span><span class="sxs-lookup"><span data-stu-id="dbd2a-151">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="dbd2a-152">对象变量值</span><span class="sxs-lookup"><span data-stu-id="dbd2a-152">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="dbd2a-153">如何： 声明对象变量并在 Visual Basic 中为其分配一个对象</span><span class="sxs-lookup"><span data-stu-id="dbd2a-153">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="dbd2a-154">如何：访问对象的成员</span><span class="sxs-lookup"><span data-stu-id="dbd2a-154">How to: Access Members of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [<span data-ttu-id="dbd2a-155">New 运算符</span><span class="sxs-lookup"><span data-stu-id="dbd2a-155">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="dbd2a-156">Option Strict 语句</span><span class="sxs-lookup"><span data-stu-id="dbd2a-156">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="dbd2a-157">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="dbd2a-157">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
