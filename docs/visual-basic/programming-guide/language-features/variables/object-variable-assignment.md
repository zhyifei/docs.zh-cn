---
title: 对象变量赋值 (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 571b09a0783ec0dfd09970b000faec39dca682b3
ms.sourcegitcommit: 4621e67f69e7a9503ea93313ff60d69683207889
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2018
ms.locfileid: "49995357"
---
# <a name="object-variable-assignment-visual-basic"></a><span data-ttu-id="eba9e-102">对象变量赋值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eba9e-102">Object Variable Assignment (Visual Basic)</span></span>
<span data-ttu-id="eba9e-103">使用普通赋值语句将对象分配给对象变量。</span><span class="sxs-lookup"><span data-stu-id="eba9e-103">You use a normal assignment statement to assign an object to an object variable.</span></span> <span data-ttu-id="eba9e-104">可以分配对象表达式或[Nothing](../../../../visual-basic/language-reference/nothing.md)关键字，如下面的示例说明了。</span><span class="sxs-lookup"><span data-stu-id="eba9e-104">You can assign an object expression or the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, as the following example illustrates.</span></span>  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 <span data-ttu-id="eba9e-105">`Nothing` 意味着没有当前分配给变量对象。</span><span class="sxs-lookup"><span data-stu-id="eba9e-105">`Nothing` means there is no object currently assigned to the variable.</span></span>  
  
## <a name="initialization"></a><span data-ttu-id="eba9e-106">初始化</span><span class="sxs-lookup"><span data-stu-id="eba9e-106">Initialization</span></span>  
 <span data-ttu-id="eba9e-107">当你的代码开始运行，您的对象变量初始化为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="eba9e-107">When your code begins running, your object variables are initialized to `Nothing`.</span></span> <span data-ttu-id="eba9e-108">这些声明中包含的初始化被重新初始化时执行的声明语句指定的值。</span><span class="sxs-lookup"><span data-stu-id="eba9e-108">Those whose declarations include initialization are reinitialized to the values you specify when the declaration statements are executed.</span></span>  
  
 <span data-ttu-id="eba9e-109">通过使用包括在声明中初始化[新建](../../../../visual-basic/language-reference/operators/new-operator.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="eba9e-109">You can include initialization in your declaration by using the [New](../../../../visual-basic/language-reference/operators/new-operator.md) keyword.</span></span> <span data-ttu-id="eba9e-110">下面的声明语句声明对象变量`testUri`和`ver`并向其分配特定的对象。</span><span class="sxs-lookup"><span data-stu-id="eba9e-110">The following declaration statements declare object variables `testUri` and `ver` and assign specific objects to them.</span></span> <span data-ttu-id="eba9e-111">每个可以使用一种合适的类的重载构造函数来初始化对象。</span><span class="sxs-lookup"><span data-stu-id="eba9e-111">Each uses one of the overloaded constructors of the appropriate class to initialize the object.</span></span>  
  
```  
Dim testUri As New System.Uri("https://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a><span data-ttu-id="eba9e-112">解除关联</span><span class="sxs-lookup"><span data-stu-id="eba9e-112">Disassociation</span></span>  
 <span data-ttu-id="eba9e-113">将对象变量设置为`Nothing`终止与任何特定对象的变量的关联。</span><span class="sxs-lookup"><span data-stu-id="eba9e-113">Setting an object variable to `Nothing` discontinues the association of the variable with any specific object.</span></span> <span data-ttu-id="eba9e-114">这会防止意外更改通过更改变量的对象。</span><span class="sxs-lookup"><span data-stu-id="eba9e-114">This prevents you from accidentally changing the object by changing the variable.</span></span> <span data-ttu-id="eba9e-115">它还允许您测试对象变量是否指向有效的对象，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="eba9e-115">It also allows you to test whether the object variable points to a valid object, as the following example shows.</span></span>  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 <span data-ttu-id="eba9e-116">如果您的变量是指该对象是另一个应用程序中，该应用程序是否已终止或只是失效的对象无法确定此测试。</span><span class="sxs-lookup"><span data-stu-id="eba9e-116">If the object your variable refers to is in another application, this test cannot determine whether that application has terminated or just invalidated the object.</span></span>  
  
 <span data-ttu-id="eba9e-117">值为对象变量`Nothing`也称为*null 引用*。</span><span class="sxs-lookup"><span data-stu-id="eba9e-117">An object variable with a value of `Nothing` is also called a *null reference*.</span></span>  
  
## <a name="current-instance"></a><span data-ttu-id="eba9e-118">当前实例</span><span class="sxs-lookup"><span data-stu-id="eba9e-118">Current Instance</span></span>  
 <span data-ttu-id="eba9e-119">*当前实例*的对象是当前正在其中执行代码。</span><span class="sxs-lookup"><span data-stu-id="eba9e-119">The *current instance* of an object is the one in which the code is currently executing.</span></span> <span data-ttu-id="eba9e-120">在过程内执行所有代码，因为当前实例是在其中调用该过程。</span><span class="sxs-lookup"><span data-stu-id="eba9e-120">Since all code executes inside a procedure, the current instance is the one in which the procedure was invoked.</span></span>  
  
 <span data-ttu-id="eba9e-121">`Me`关键字作为对象变量引用当前实例。</span><span class="sxs-lookup"><span data-stu-id="eba9e-121">The `Me` keyword acts as an object variable referring to the current instance.</span></span> <span data-ttu-id="eba9e-122">如果不是一个过程[共享](../../../../visual-basic/language-reference/modifiers/shared.md)，可以使用`Me`关键字来获取当前实例的指针。</span><span class="sxs-lookup"><span data-stu-id="eba9e-122">If a procedure is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), it can use the `Me` keyword to obtain a pointer to the current instance.</span></span> <span data-ttu-id="eba9e-123">共享的过程不能与类的特定实例相关联。</span><span class="sxs-lookup"><span data-stu-id="eba9e-123">Shared procedures cannot be associated with a specific instance of a class.</span></span>  
  
 <span data-ttu-id="eba9e-124">使用`Me`对于当前的实例传递到另一个模块中的过程非常有用。</span><span class="sxs-lookup"><span data-stu-id="eba9e-124">Using `Me` is particularly useful for passing the current instance to a procedure in another module.</span></span> <span data-ttu-id="eba9e-125">例如，假设你有多个 XML 文档，想要将一些标准文本添加到所有这些。</span><span class="sxs-lookup"><span data-stu-id="eba9e-125">For example, suppose you have a number of XML documents and wish to add some standard text to all of them.</span></span> <span data-ttu-id="eba9e-126">下面的示例定义一个过程来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="eba9e-126">The following example defines a procedure to do this.</span></span>  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 <span data-ttu-id="eba9e-127">然后，每个 XML 文档对象无法调用该过程，并作为参数传递它的当前实例。</span><span class="sxs-lookup"><span data-stu-id="eba9e-127">Every XML document object could then call the procedure and pass its current instance as an argument.</span></span> <span data-ttu-id="eba9e-128">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="eba9e-128">The following example demonstrates this.</span></span>  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a><span data-ttu-id="eba9e-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="eba9e-129">See Also</span></span>  
 [<span data-ttu-id="eba9e-130">对象变量</span><span class="sxs-lookup"><span data-stu-id="eba9e-130">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="eba9e-131">对象变量声明</span><span class="sxs-lookup"><span data-stu-id="eba9e-131">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="eba9e-132">对象变量值</span><span class="sxs-lookup"><span data-stu-id="eba9e-132">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [<span data-ttu-id="eba9e-133">如何： 声明对象变量并在 Visual Basic 中为其分配对象</span><span class="sxs-lookup"><span data-stu-id="eba9e-133">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [<span data-ttu-id="eba9e-134">如何：使对象变量不引用任何实例</span><span class="sxs-lookup"><span data-stu-id="eba9e-134">How to: Make an Object Variable Not Refer to Any Instance</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [<span data-ttu-id="eba9e-135">Me、My、MyBase 和 MyClass</span><span class="sxs-lookup"><span data-stu-id="eba9e-135">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
