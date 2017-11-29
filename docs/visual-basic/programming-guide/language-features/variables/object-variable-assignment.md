---
title: "对象变量赋值 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb6b53bebddc1c9cf1b9088e96ded36a5e1c5242
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="4f644-102">对象变量赋值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f644-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="4f644-103">你可以使用普通赋值语句将对象分配给对象变量。</span><span class="sxs-lookup"><span data-stu-id="4f644-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="4f644-104">你可以分配对象表达式或[执行任何操作](../../../../visual-basic/language-reference/nothing.md)关键字，如下面的示例演示。</span><span class="sxs-lookup"><span data-stu-id="4f644-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="4f644-105">`Nothing`意味着没有当前分配给变量对象。</span><span class="sxs-lookup"><span data-stu-id="4f644-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="4f644-106">初始化</span><span class="sxs-lookup"><span data-stu-id="4f644-106">Initialization</span></span>  
 <span data-ttu-id="4f644-107">当你的代码开始运行，你的对象变量将初始化为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="4f644-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="4f644-108">这些声明中包含的初始化被重新初始化为指定的声明语句执行时的值。</span><span class="sxs-lookup"><span data-stu-id="4f644-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="4f644-109">您可以通过使用包括的声明初始化[新建](../../../../visual-basic/language-reference/operators/new-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="4f644-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="4f644-110">下面的声明语句声明对象变量`testUri`和`ver`并向它们分配特定的对象。</span><span class="sxs-lookup"><span data-stu-id="4f644-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="4f644-111">每个可以使用一种适当的类的重载构造函数来初始化对象。</span><span class="sxs-lookup"><span data-stu-id="4f644-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="4f644-112">解除关联</span><span class="sxs-lookup"><span data-stu-id="4f644-112">Disassociation</span></span>  
 <span data-ttu-id="4f644-113">将对象变量设置为`Nothing`终止与任何特定的对象变量的关联。</span><span class="sxs-lookup"><span data-stu-id="4f644-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="4f644-114">这会防止意外更改通过更改变量的对象。</span><span class="sxs-lookup"><span data-stu-id="4f644-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="4f644-115">它还允许你可以测试是否对象变量指向有效的对象，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="4f644-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="4f644-116">如果你变量引用的对象是在另一个应用程序中，无法确定此测试，该应用程序是否已终止或只需失效的对象。</span><span class="sxs-lookup"><span data-stu-id="4f644-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="4f644-117">对象变量值为`Nothing`也被称为*null 引用*。</span><span class="sxs-lookup"><span data-stu-id="4f644-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="4f644-118">当前实例</span><span class="sxs-lookup"><span data-stu-id="4f644-118">Current Instance</span></span>  
 <span data-ttu-id="4f644-119">*当前实例*的对象是当前在其中执行代码。</span><span class="sxs-lookup"><span data-stu-id="4f644-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="4f644-120">由于所有代码的都执行过程内，当前实例是在其中调用此过程。</span><span class="sxs-lookup"><span data-stu-id="4f644-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="4f644-121">`Me`关键字作为引用的当前实例的对象变量。</span><span class="sxs-lookup"><span data-stu-id="4f644-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="4f644-122">如果不是一个过程[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，它可以使用`Me`关键字用于获取指向当前实例。</span><span class="sxs-lookup"><span data-stu-id="4f644-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="4f644-123">共享的过程不能与类的特定实例关联。</span><span class="sxs-lookup"><span data-stu-id="4f644-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="4f644-124">使用`Me`很适合用于将当前实例传递给另一个模块中的过程。</span><span class="sxs-lookup"><span data-stu-id="4f644-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="4f644-125">例如，假设你有大量的 XML 文档，想要将一些标准的文本添加到所有这些。</span><span class="sxs-lookup"><span data-stu-id="4f644-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="4f644-126">下面的示例定义一个过程来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4f644-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="4f644-127">然后，每个 XML 文档对象无法调用的过程，并将它的当前实例作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="4f644-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="4f644-128">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="4f644-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="4f644-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f644-129">See Also</span></span>  
 [<span data-ttu-id="4f644-130">对象变量</span><span class="sxs-lookup"><span data-stu-id="4f644-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="4f644-131">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="4f644-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="4f644-132">对象变量值</span><span class="sxs-lookup"><span data-stu-id="4f644-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="4f644-133">如何： 声明对象变量并在 Visual Basic 中为其分配一个对象</span><span class="sxs-lookup"><span data-stu-id="4f644-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="4f644-134">如何：使对象变量不引用任何实例</span><span class="sxs-lookup"><span data-stu-id="4f644-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="4f644-135">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="4f644-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
