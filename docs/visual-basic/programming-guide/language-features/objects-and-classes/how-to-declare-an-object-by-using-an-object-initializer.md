---
title: "如何：使用对象初始值设定项声明对象 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87c818765cbeac7a3080ee666d464052493e5bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="83e63-102">如何：使用对象初始值设定项声明对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83e63-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="83e63-103">对象初始值设定项，可以声明并实例化单个语句中的类的实例。</span><span class="sxs-lookup"><span data-stu-id="83e63-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="83e63-104">此外，可以但不调用参数化构造函数一次初始化实例的一个或多个的成员。</span><span class="sxs-lookup"><span data-stu-id="83e63-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="83e63-105">当使用对象初始值设定项来创建命名类型的实例时，被调用跟你指定的顺序中的指定成员的初始化的类的默认构造函数。</span><span class="sxs-lookup"><span data-stu-id="83e63-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="83e63-106">下面的过程演示如何创建的实例`Student`三个不同的方式的类。</span><span class="sxs-lookup"><span data-stu-id="83e63-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="83e63-107">此类具有名字、 姓氏和类年属性，以及其他。</span><span class="sxs-lookup"><span data-stu-id="83e63-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="83e63-108">每三个声明创建的新实例`Student`，与属性`First`设置为"Michael"，属性`Last`设置为"Tucker"，并且所有其他成员设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="83e63-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="83e63-109">在过程中每个声明的结果等效于以下示例中，这个过程未使用的对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="83e63-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 <span data-ttu-id="83e63-110">实现的`Student`类，请参阅[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="83e63-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="83e63-111">您可以从该主题可以将设置类创建的列表中复制代码`Student`要使用的对象。</span><span class="sxs-lookup"><span data-stu-id="83e63-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="83e63-112">若要使用对象初始值设定项中创建命名类的对象</span><span class="sxs-lookup"><span data-stu-id="83e63-112">To create an object of a named class by using an object initializer</span></span>  
  
1.  <span data-ttu-id="83e63-113">就像你计划使用构造函数，请开始声明。</span><span class="sxs-lookup"><span data-stu-id="83e63-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2.  <span data-ttu-id="83e63-114">键入关键字`With`后, 跟一个大括号内的初始化列表。</span><span class="sxs-lookup"><span data-stu-id="83e63-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  <span data-ttu-id="83e63-115">在初始化列表中，包括每个你想要初始化，并为其分配的初始值的属性。</span><span class="sxs-lookup"><span data-stu-id="83e63-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="83e63-116">属性的名称以句点开头。</span><span class="sxs-lookup"><span data-stu-id="83e63-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     <span data-ttu-id="83e63-117">你可以初始化类的一个或多个成员。</span><span class="sxs-lookup"><span data-stu-id="83e63-117">You can initialize one or more members of the class.</span></span>  
  
4.  <span data-ttu-id="83e63-118">或者，你可以声明类的新实例，然后将值分配给它。</span><span class="sxs-lookup"><span data-stu-id="83e63-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="83e63-119">首先，声明的实例`Student`:</span><span class="sxs-lookup"><span data-stu-id="83e63-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5.  <span data-ttu-id="83e63-120">开始创建的实例`Student`以正常方式。</span><span class="sxs-lookup"><span data-stu-id="83e63-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6.  <span data-ttu-id="83e63-121">类型`With`，然后对象初始值设定项的新实例的一个或多个成员进行初始化。</span><span class="sxs-lookup"><span data-stu-id="83e63-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  <span data-ttu-id="83e63-122">你可以通过省略简化上一步中的定义`As Student`。</span><span class="sxs-lookup"><span data-stu-id="83e63-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="83e63-123">如果执行此操作时，编译器确定`student3`是的一个实例`Student`使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="83e63-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     <span data-ttu-id="83e63-124">有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="83e63-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e63-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83e63-125">See Also</span></span>  
 [<span data-ttu-id="83e63-126">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="83e63-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="83e63-127">如何：创建项列表</span><span class="sxs-lookup"><span data-stu-id="83e63-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [<span data-ttu-id="83e63-128">对象初始值设定项：命名类型和匿名类型</span><span class="sxs-lookup"><span data-stu-id="83e63-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [<span data-ttu-id="83e63-129">匿名类型</span><span class="sxs-lookup"><span data-stu-id="83e63-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
