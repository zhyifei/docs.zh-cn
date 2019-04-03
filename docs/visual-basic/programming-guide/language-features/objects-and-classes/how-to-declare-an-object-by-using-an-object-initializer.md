---
title: 如何：将对象声明使用对象初始值设定项 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 314706207800b2e86aa0032a52d8c50fbb726887
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825127"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a><span data-ttu-id="0acb7-102">如何：将对象声明使用对象初始值设定项 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0acb7-102">How to: Declare an Object by Using an Object Initializer (Visual Basic)</span></span>
<span data-ttu-id="0acb7-103">对象初始值设定项，可以声明并实例化单个语句中类的实例。</span><span class="sxs-lookup"><span data-stu-id="0acb7-103">Object initializers enable you to declare and instantiate an instance of a class in a single statement.</span></span> <span data-ttu-id="0acb7-104">此外，可以不调用参数化构造函数的情况下一次初始化实例的一个或多个成员。</span><span class="sxs-lookup"><span data-stu-id="0acb7-104">In addition, you can initialize one or more members of the instance at the same time, without invoking a parameterized constructor.</span></span>  
  
 <span data-ttu-id="0acb7-105">当使用对象初始值设定项来创建已命名类型的实例时，将调用类的默认构造函数，跟您指定的顺序的指定成员的初始化。</span><span class="sxs-lookup"><span data-stu-id="0acb7-105">When you use an object initializer to create an instance of a named type, the default constructor for the class is called, followed by initialization of designated members in the order you specify.</span></span>  
  
 <span data-ttu-id="0acb7-106">下面的过程演示如何创建的实例`Student`三种不同方式的类。</span><span class="sxs-lookup"><span data-stu-id="0acb7-106">The following procedure shows how to create an instance of a `Student` class in three different ways.</span></span> <span data-ttu-id="0acb7-107">类具有名字、 姓氏和类年属性，等等。</span><span class="sxs-lookup"><span data-stu-id="0acb7-107">The class has first name, last name, and class year properties, among others.</span></span> <span data-ttu-id="0acb7-108">三个声明的每个创建的新实例`Student`，使用属性`First`设置为"Michael"，属性`Last`设置为"Tucker"，并且所有其他成员设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="0acb7-108">Each of the three declarations creates a new instance of `Student`, with property `First` set to "Michael", property `Last` set to "Tucker", and all other members set to their default values.</span></span> <span data-ttu-id="0acb7-109">在过程中每个声明的结果等效于以下示例中，不使用对象初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="0acb7-109">The result of each declaration in the procedure is equivalent to the following example, which does not use an object initializer.</span></span>  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 <span data-ttu-id="0acb7-110">实现`Student`类，请参阅[如何：创建的项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。</span><span class="sxs-lookup"><span data-stu-id="0acb7-110">For an implementation of the `Student` class, see [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="0acb7-111">可以将代码复制从该主题设置类并创建一系列`Student`要使用的对象。</span><span class="sxs-lookup"><span data-stu-id="0acb7-111">You can copy the code from that topic to set up the class and create a list of `Student` objects to work with.</span></span>  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a><span data-ttu-id="0acb7-112">若要使用对象初始值设定项创建的已命名的类对象</span><span class="sxs-lookup"><span data-stu-id="0acb7-112">To create an object of a named class by using an object initializer</span></span>  
  
1.  <span data-ttu-id="0acb7-113">开始声明，因为如果您计划使用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="0acb7-113">Begin the declaration as if you planned to use a constructor.</span></span>  
  
     `Dim student1 As New Student`  
  
2.  <span data-ttu-id="0acb7-114">键入的关键字`With`后, 跟一个大括号括起来的初始化列表。</span><span class="sxs-lookup"><span data-stu-id="0acb7-114">Type the keyword `With`, followed by an initialization list in braces.</span></span>  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  <span data-ttu-id="0acb7-115">在初始化列表中，包括每个属性，你想要初始化并向其分配初始值。</span><span class="sxs-lookup"><span data-stu-id="0acb7-115">In the initialization list, include each property that you want to initialize and assign an initial value to it.</span></span> <span data-ttu-id="0acb7-116">属性的名称以句点开头。</span><span class="sxs-lookup"><span data-stu-id="0acb7-116">The name of the property is preceded by a period.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     <span data-ttu-id="0acb7-117">您可以初始化类的一个或多个成员。</span><span class="sxs-lookup"><span data-stu-id="0acb7-117">You can initialize one or more members of the class.</span></span>  
  
4.  <span data-ttu-id="0acb7-118">或者，可以声明类的新实例，然后将值分配给它。</span><span class="sxs-lookup"><span data-stu-id="0acb7-118">Alternatively, you can declare a new instance of the class and then assign a value to it.</span></span> <span data-ttu-id="0acb7-119">首先，声明的实例`Student`:</span><span class="sxs-lookup"><span data-stu-id="0acb7-119">First, declare an instance of `Student`:</span></span>  
  
     `Dim student2 As Student`  
  
5.  <span data-ttu-id="0acb7-120">开始创建的实例`Student`以正常方式。</span><span class="sxs-lookup"><span data-stu-id="0acb7-120">Begin the creation of an instance of `Student` in the normal way.</span></span>  
  
     `Dim student2 As Student = New Student`  
  
6.  <span data-ttu-id="0acb7-121">类型`With`，然后对象初始值设定项的新实例的一个或多个成员进行初始化。</span><span class="sxs-lookup"><span data-stu-id="0acb7-121">Type `With` and then an object initializer to initialize one or more members of the new instance.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7.  <span data-ttu-id="0acb7-122">你可以通过省略来简化上一步中的定义`As Student`。</span><span class="sxs-lookup"><span data-stu-id="0acb7-122">You can simplify the definition in the previous step by omitting `As Student`.</span></span> <span data-ttu-id="0acb7-123">如果这样做，编译器确定`student3`的一个实例`Student`使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="0acb7-123">If you do this, the compiler determines that `student3` is an instance of `Student` by using local type inference.</span></span>  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     <span data-ttu-id="0acb7-124">有关详细信息，请参阅[本地类型推断](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。</span><span class="sxs-lookup"><span data-stu-id="0acb7-124">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0acb7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0acb7-125">See also</span></span>

- [<span data-ttu-id="0acb7-126">局部类型推理</span><span class="sxs-lookup"><span data-stu-id="0acb7-126">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="0acb7-127">如何：创建的项的列表</span><span class="sxs-lookup"><span data-stu-id="0acb7-127">How to: Create a List of Items</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [<span data-ttu-id="0acb7-128">对象初始值设定项：命名和匿名类型</span><span class="sxs-lookup"><span data-stu-id="0acb7-128">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="0acb7-129">匿名类型</span><span class="sxs-lookup"><span data-stu-id="0acb7-129">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
