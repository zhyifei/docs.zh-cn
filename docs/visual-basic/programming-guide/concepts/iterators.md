---
title: "迭代器 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c38609878c10ff3234b5a33ec44d678d24c11d7f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="iterators-visual-basic"></a><span data-ttu-id="c7382-102">迭代器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7382-102">Iterators (Visual Basic)</span></span>
<span data-ttu-id="c7382-103">*迭代器*可用于单步执行集合如列出和数组。</span><span class="sxs-lookup"><span data-stu-id="c7382-103">An *iterator* can be used to step through collections such as lists and arrays.</span></span>  
  
 <span data-ttu-id="c7382-104">迭代器方法或`get`访问器在集合上执行自定义的迭代。</span><span class="sxs-lookup"><span data-stu-id="c7382-104">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="c7382-105">迭代器方法使用[生成](../../../visual-basic/language-reference/statements/yield-statement.md)语句可一次返回每个元素。</span><span class="sxs-lookup"><span data-stu-id="c7382-105">An iterator method uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element one at a time.</span></span> <span data-ttu-id="c7382-106">当`Yield`到达语句，记住代码中的当前位置。</span><span class="sxs-lookup"><span data-stu-id="c7382-106">When a `Yield` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="c7382-107">在下次调用迭代器函数将从该位置重新开始执行。</span><span class="sxs-lookup"><span data-stu-id="c7382-107">Execution is restarted from that location the next time the iterator function is called.</span></span>  
  
 <span data-ttu-id="c7382-108">通过使用从客户端代码的迭代器[为每个...下一步](../../../visual-basic/language-reference/statements/for-each-next-statement.md)语句中，还是通过使用 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="c7382-108">You consume an iterator from client code by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement, or by using a LINQ query.</span></span>  
  
 <span data-ttu-id="c7382-109">在下面的示例中，第一次迭代`For Each`循环会导致执行按部就班地进行`SomeNumbers`直到第一个迭代器方法`Yield`到达语句。</span><span class="sxs-lookup"><span data-stu-id="c7382-109">In the following example, the first iteration of the `For Each` loop causes execution to proceed  in the `SomeNumbers` iterator method until the first `Yield` statement is reached.</span></span> <span data-ttu-id="c7382-110">此迭代返回的值为 3，且不保留当前在迭代器方法的位置。</span><span class="sxs-lookup"><span data-stu-id="c7382-110">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="c7382-111">在循环的下一个迭代，迭代器方法中的执行将继续从何处中断，达到时再次停止`Yield`语句。</span><span class="sxs-lookup"><span data-stu-id="c7382-111">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="c7382-112">此迭代返回值为 5，并再次保留当前在迭代器方法的位置。</span><span class="sxs-lookup"><span data-stu-id="c7382-112">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="c7382-113">在循环完成时到达迭代器方法的末尾。</span><span class="sxs-lookup"><span data-stu-id="c7382-113">The loop completes when the end of the iterator method is reached.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 <span data-ttu-id="c7382-114">迭代器方法的返回类型或`get`取值函数可以是<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="c7382-114">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
 <span data-ttu-id="c7382-115">您可以使用`Exit Function`或`Return`语句来终止迭代。</span><span class="sxs-lookup"><span data-stu-id="c7382-115">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="c7382-116">Visual Basic 迭代器函数或`get`取值函数声明中包括[迭代器](../../../visual-basic/language-reference/modifiers/iterator.md)修饰符。</span><span class="sxs-lookup"><span data-stu-id="c7382-116">A Visual Basic iterator function or `get` accessor declaration includes an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
 <span data-ttu-id="c7382-117">在 Visual Studio 2012 中的 Visual Basic 中引入了迭代器。</span><span class="sxs-lookup"><span data-stu-id="c7382-117">Iterators were introduced in Visual Basic in Visual Studio 2012.</span></span>  
  
 <span data-ttu-id="c7382-118">**主题内容**</span><span class="sxs-lookup"><span data-stu-id="c7382-118">**In this topic**</span></span>  
  
-   [<span data-ttu-id="c7382-119">简单的迭代器</span><span class="sxs-lookup"><span data-stu-id="c7382-119">Simple Iterator</span></span>](#BKMK_SimpleIterator)  
  
-   [<span data-ttu-id="c7382-120">创建集合类</span><span class="sxs-lookup"><span data-stu-id="c7382-120">Creating a Collection Class</span></span>](#BKMK_CollectionClass)  
  
-   [<span data-ttu-id="c7382-121">Try 块</span><span class="sxs-lookup"><span data-stu-id="c7382-121">Try Blocks</span></span>](#BKMK_TryBlocks)  
  
-   [<span data-ttu-id="c7382-122">匿名方法</span><span class="sxs-lookup"><span data-stu-id="c7382-122">Anonymous Methods</span></span>](#BKMK_AnonymousMethods)  
  
-   [<span data-ttu-id="c7382-123">对泛型列表使用迭代器</span><span class="sxs-lookup"><span data-stu-id="c7382-123">Using Iterators with a Generic List</span></span>](#BKMK_GenericList)  
  
-   [<span data-ttu-id="c7382-124">语法信息</span><span class="sxs-lookup"><span data-stu-id="c7382-124">Syntax Information</span></span>](#BKMK_SyntaxInformation)  
  
-   [<span data-ttu-id="c7382-125">技术实现</span><span class="sxs-lookup"><span data-stu-id="c7382-125">Technical Implementation</span></span>](#BKMK_Technical)  
  
-   [<span data-ttu-id="c7382-126">迭代器的使用</span><span class="sxs-lookup"><span data-stu-id="c7382-126">Use of Iterators</span></span>](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  <span data-ttu-id="c7382-127">除了简单的迭代器示例主题中的所有示例，包括[导入](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)语句`System.Collections`和`System.Collections.Generic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="c7382-127">For all examples in the topic except the Simple Iterator example, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>  
  
##  <span data-ttu-id="c7382-128"><a name="BKMK_SimpleIterator"></a>简单的迭代器</span><span class="sxs-lookup"><span data-stu-id="c7382-128"><a name="BKMK_SimpleIterator"></a> Simple Iterator</span></span>  
 <span data-ttu-id="c7382-129">下面的示例都有一个`Yield`内的语句[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。</span><span class="sxs-lookup"><span data-stu-id="c7382-129">The following example has a single `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="c7382-130">在`Main`，每次迭代`For Each`语句体创建了迭代器函数，它将继续到下一个调用`Yield`语句。</span><span class="sxs-lookup"><span data-stu-id="c7382-130">In `Main`, each iteration of the `For Each` statement body creates a call to the iterator function, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
##  <span data-ttu-id="c7382-131"><a name="BKMK_CollectionClass"></a>创建集合类</span><span class="sxs-lookup"><span data-stu-id="c7382-131"><a name="BKMK_CollectionClass"></a> Creating a Collection Class</span></span>  
 <span data-ttu-id="c7382-132">在下面的示例中，`DaysOfTheWeek`类实现<xref:System.Collections.IEnumerable>接口，它要求<xref:System.Collections.IEnumerable.GetEnumerator%2A>方法。</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="c7382-132">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="c7382-133">编译器隐式调用`GetEnumerator`方法，它返回<xref:System.Collections.IEnumerator>。</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c7382-133">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>  
  
 <span data-ttu-id="c7382-134">`GetEnumerator`方法通过使用一次返回每个字符串之一`Yield`语句中，和一个`Iterator`修饰符是函数声明中。</span><span class="sxs-lookup"><span data-stu-id="c7382-134">The `GetEnumerator` method returns each string one at a time by using the `Yield` statement, and  an `Iterator` modifier is in the function declaration.</span></span>  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 <span data-ttu-id="c7382-135">下面的示例创建`Zoo`类，该类包含动物的集合。</span><span class="sxs-lookup"><span data-stu-id="c7382-135">The following example creates a `Zoo` class that contains a collection of animals.</span></span>  
  
 <span data-ttu-id="c7382-136">`For Each`引用类实例的语句 (`theZoo`) 隐式调用`GetEnumerator`方法。</span><span class="sxs-lookup"><span data-stu-id="c7382-136">The `For Each` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="c7382-137">`For Each`语句，请参阅`Birds`和`Mammals`属性使用`AnimalsForType`名为迭代器方法。</span><span class="sxs-lookup"><span data-stu-id="c7382-137">The `For Each` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
##  <span data-ttu-id="c7382-138"><a name="BKMK_TryBlocks"></a>Try 块</span><span class="sxs-lookup"><span data-stu-id="c7382-138"><a name="BKMK_TryBlocks"></a> Try Blocks</span></span>  
 <span data-ttu-id="c7382-139">Visual Basic 将允许`Yield`中的语句`Try`块[重试...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c7382-139">Visual Basic allows a `Yield` statement in the `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="c7382-140">一个`Try`具有的块`Yield`语句可以有`Catch`阻止，并且也能`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="c7382-140">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="c7382-141">下面的示例包含`Try`， `Catch`，和`Finally`块在迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="c7382-141">The following example includes `Try`, `Catch`, and `Finally` blocks in an iterator function.</span></span> <span data-ttu-id="c7382-142">`Finally`之前执行的迭代器函数中的块`For Each`迭代完成。</span><span class="sxs-lookup"><span data-stu-id="c7382-142">The `Finally` block in the iterator function executes before the `For Each` iteration finishes.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 <span data-ttu-id="c7382-143">一个`Yield`语句不能包含在内`Catch`块或`Finally`块。</span><span class="sxs-lookup"><span data-stu-id="c7382-143">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="c7382-144">如果`For Each`（而不是迭代器方法中） 的主体引发了异常，`Catch`未执行迭代器函数中的块，但`Finally`执行迭代器函数中的块。</span><span class="sxs-lookup"><span data-stu-id="c7382-144">If the `For Each` body (instead of the iterator method) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="c7382-145">一个`Catch`迭代器函数内部的块将捕获在迭代器函数内部发生的异常。</span><span class="sxs-lookup"><span data-stu-id="c7382-145">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
##  <span data-ttu-id="c7382-146"><a name="BKMK_AnonymousMethods"></a>匿名方法</span><span class="sxs-lookup"><span data-stu-id="c7382-146"><a name="BKMK_AnonymousMethods"></a> Anonymous Methods</span></span>  
 <span data-ttu-id="c7382-147">在 Visual Basic 中，一个匿名函数可以是一个迭代器函数。</span><span class="sxs-lookup"><span data-stu-id="c7382-147">In Visual Basic, an anonymous function can be an iterator function.</span></span> <span data-ttu-id="c7382-148">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="c7382-148">The following example illustrates this.</span></span>  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 <span data-ttu-id="c7382-149">下面的示例有一个对参数进行验证的非迭代器方法。</span><span class="sxs-lookup"><span data-stu-id="c7382-149">The following example has a non-iterator method that validates the arguments.</span></span> <span data-ttu-id="c7382-150">该方法返回一个匿名的迭代器，描述集合元素的结果。</span><span class="sxs-lookup"><span data-stu-id="c7382-150">The method returns the result of an anonymous iterator that describes the collection elements.</span></span>  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 <span data-ttu-id="c7382-151">如果验证改为在迭代器函数中，不能只有第一次迭代开始时才执行验证`For Each`正文。</span><span class="sxs-lookup"><span data-stu-id="c7382-151">If validation is instead inside the iterator function, the validation cannot be performed until the start of the first iteration of the `For Each` body.</span></span>  
  
##  <span data-ttu-id="c7382-152"><a name="BKMK_GenericList"></a>对泛型列表使用迭代器</span><span class="sxs-lookup"><span data-stu-id="c7382-152"><a name="BKMK_GenericList"></a> Using Iterators with a Generic List</span></span>  
 <span data-ttu-id="c7382-153">在下面的示例中，`Stack(Of T)`泛型类实现<xref:System.Collections.Generic.IEnumerable%601>泛型接口。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c7382-153">In the following example, the `Stack(Of T)` generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="c7382-154">`Push`方法将值分配给类型的数组`T`。</span><span class="sxs-lookup"><span data-stu-id="c7382-154">The `Push` method assigns values to an array of type `T`.</span></span> <span data-ttu-id="c7382-155"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>方法通过使用返回的数组值`Yield`语句。</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="c7382-155">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `Yield` statement.</span></span>  
  
 <span data-ttu-id="c7382-156">除了泛型<xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>方法时，非泛型<xref:System.Collections.IEnumerable.GetEnumerator%2A>还必须实现方法。</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A></span><span class="sxs-lookup"><span data-stu-id="c7382-156">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="c7382-157">这是因为<xref:System.Collections.Generic.IEnumerable%601>从<xref:System.Collections.IEnumerable>。</xref:System.Collections.IEnumerable>继承</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c7382-157">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="c7382-158">非泛型实现服从的通用实现。</span><span class="sxs-lookup"><span data-stu-id="c7382-158">The non-generic implementation defers to the generic implementation.</span></span>  
  
 <span data-ttu-id="c7382-159">该示例使用命名的迭代器来支持循环访问同一数据集合的各种方法。</span><span class="sxs-lookup"><span data-stu-id="c7382-159">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="c7382-160">这两个命名的迭代器是`TopToBottom`和`BottomToTop`属性，与`TopN`方法。</span><span class="sxs-lookup"><span data-stu-id="c7382-160">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>  
  
 <span data-ttu-id="c7382-161">`BottomToTop`属性声明包含`Iterator`关键字。</span><span class="sxs-lookup"><span data-stu-id="c7382-161">The `BottomToTop` property declaration includes the `Iterator` keyword.</span></span>  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
  
```  
  
##  <span data-ttu-id="c7382-162"><a name="BKMK_SyntaxInformation"></a>语法信息</span><span class="sxs-lookup"><span data-stu-id="c7382-162"><a name="BKMK_SyntaxInformation"></a> Syntax Information</span></span>  
 <span data-ttu-id="c7382-163">迭代器可作为一种方法或`get`取值函数。</span><span class="sxs-lookup"><span data-stu-id="c7382-163">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="c7382-164">迭代器在事件、 实例构造函数、 静态构造函数或静态析构函数不能出现。</span><span class="sxs-lookup"><span data-stu-id="c7382-164">An iterator cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="c7382-165">中的表达式类型必须存在的隐式转换`Yield`语句将返回迭代器的类型。</span><span class="sxs-lookup"><span data-stu-id="c7382-165">An implicit conversion must exist from the expression type in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="c7382-166">在 Visual Basic 中，迭代器方法不能有任何`ByRef`参数。</span><span class="sxs-lookup"><span data-stu-id="c7382-166">In Visual Basic, an iterator method cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="c7382-167">在 Visual Basic 程序"让步"不是保留的字并且仅当使用中具有特殊含义`Iterator`方法或`get`取值函数。</span><span class="sxs-lookup"><span data-stu-id="c7382-167">In Visual Basic, "Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` method or `get` accessor.</span></span>  
  
##  <span data-ttu-id="c7382-168"><a name="BKMK_Technical"></a>技术实现</span><span class="sxs-lookup"><span data-stu-id="c7382-168"><a name="BKMK_Technical"></a> Technical Implementation</span></span>  
 <span data-ttu-id="c7382-169">尽管您编写的迭代器作为一种方法，编译器将它转换嵌套类，它是，实际上，状态机。</span><span class="sxs-lookup"><span data-stu-id="c7382-169">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="c7382-170">此类跟踪的迭代器作为多长时间的位置`For Each...Next`客户端代码中的循环继续进行。</span><span class="sxs-lookup"><span data-stu-id="c7382-170">This class keeps track of the position of the iterator as long the `For Each...Next` loop in the client code continues.</span></span>  
  
 <span data-ttu-id="c7382-171">若要查看的编译器会执行，可以使用 Ildasm.exe 工具查看为迭代器方法生成的 Microsoft 中间语言代码。</span><span class="sxs-lookup"><span data-stu-id="c7382-171">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that is generated for an iterator method.</span></span>  
  
 <span data-ttu-id="c7382-172">当您创建的迭代器的[类](../../../csharp/language-reference/keywords/class.md)或[结构](../../../csharp/language-reference/keywords/struct.md)，不需要实现整个<xref:System.Collections.IEnumerator>接口。</xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c7382-172">When you create an iterator for a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md), you do not have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="c7382-173">当编译器检测到迭代器时，它自动生成`Current`， `MoveNext`，和`Dispose`方法<xref:System.Collections.IEnumerator>或<xref:System.Collections.Generic.IEnumerator%601>接口。</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="c7382-173">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>  
  
 <span data-ttu-id="c7382-174">上的每次后续迭代`For Each…Next`循环 (或直接调用`IEnumerator.MoveNext`) 下, 一个迭代器代码主体将在上一个后恢复`Yield`语句。</span><span class="sxs-lookup"><span data-stu-id="c7382-174">On each successive iteration of the `For Each…Next` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `Yield` statement.</span></span> <span data-ttu-id="c7382-175">然后继续下一个`Yield`语句之前已到达迭代器主体的结尾，或直到`Exit Function`或`Return`遇到语句。</span><span class="sxs-lookup"><span data-stu-id="c7382-175">It then continues to the next `Yield` statement until the end of the iterator body is reached, or until an `Exit Function` or `Return` statement is encountered.</span></span>  
  
 <span data-ttu-id="c7382-176">不支持迭代器<xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>方法。</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c7382-176">Iterators do not support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="c7382-177">若要重新循环从一开始，你必须获取新的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c7382-177">To re-iterate from the start, you must obtain a new iterator.</span></span>  
  
 <span data-ttu-id="c7382-178">有关其他信息，请参阅[Visual Basic 语言规范](../../../visual-basic/reference/language-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="c7382-178">For additional information, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
##  <span data-ttu-id="c7382-179"><a name="BKMK_UseOfIterators"></a>迭代器的使用</span><span class="sxs-lookup"><span data-stu-id="c7382-179"><a name="BKMK_UseOfIterators"></a> Use of Iterators</span></span>  
 <span data-ttu-id="c7382-180">迭代器使您能够维护的简单性`For Each`时需要使用复杂的代码来填充列表序列循环。</span><span class="sxs-lookup"><span data-stu-id="c7382-180">Iterators enable you to maintain the simplicity of a `For Each` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="c7382-181">当想要执行下列操作时，这很有用︰</span><span class="sxs-lookup"><span data-stu-id="c7382-181">This can be useful when you want to do the following:</span></span>  
  
-   <span data-ttu-id="c7382-182">在第一个之后修改列表序列`For Each`循环迭代。</span><span class="sxs-lookup"><span data-stu-id="c7382-182">Modify the list sequence after the first `For Each` loop iteration.</span></span>  
  
-   <span data-ttu-id="c7382-183">避免完全加载之前的第一个迭代的大型列表`For Each`循环。</span><span class="sxs-lookup"><span data-stu-id="c7382-183">Avoid fully loading a large list before the first iteration of a `For Each` loop.</span></span> <span data-ttu-id="c7382-184">一个示例是分页的提取要加载一批表行。</span><span class="sxs-lookup"><span data-stu-id="c7382-184">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="c7382-185">另一个示例是<xref:System.IO.DirectoryInfo.EnumerateFiles%2A>方法，该实现在.NET Framework 中的迭代器方法。</xref:System.IO.DirectoryInfo.EnumerateFiles%2A></span><span class="sxs-lookup"><span data-stu-id="c7382-185">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators within the .NET Framework.</span></span>  
  
-   <span data-ttu-id="c7382-186">封装构建的列表中迭代器。</span><span class="sxs-lookup"><span data-stu-id="c7382-186">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="c7382-187">在迭代器方法中，可以生成该列表，并让行在循环中的每个结果。</span><span class="sxs-lookup"><span data-stu-id="c7382-187">In the iterator method, you can build the list and then yield each result in a loop.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7382-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7382-188">See Also</span></span>  
 <span data-ttu-id="c7382-189"><xref:System.Collections.Generic></xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="c7382-189"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="c7382-190"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="c7382-190"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="c7382-191"> [每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c7382-191"> [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="c7382-192"> [Yield 语句](../../../visual-basic/language-reference/statements/yield-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c7382-192"> [Yield Statement](../../../visual-basic/language-reference/statements/yield-statement.md) </span></span>  
<span data-ttu-id="c7382-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span><span class="sxs-lookup"><span data-stu-id="c7382-193"> [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)</span></span>
