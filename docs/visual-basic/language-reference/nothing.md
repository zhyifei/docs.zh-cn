---
title: Nothing (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: b4a9acb5a43898ef616bbc6bb97f2f4f96d206b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496944"
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="0c12b-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c12b-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="0c12b-103">表示任何数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="0c12b-103">Represents the default value of any data type.</span></span> <span data-ttu-id="0c12b-104">对于引用类型，默认值是`null`引用。</span><span class="sxs-lookup"><span data-stu-id="0c12b-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="0c12b-105">对于值类型，默认值取决于值类型是否可以为 null。</span><span class="sxs-lookup"><span data-stu-id="0c12b-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c12b-106">对于不可为 null 的值类型，`Nothing`在 Visual Basic 中不同于`null`中C#。</span><span class="sxs-lookup"><span data-stu-id="0c12b-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="0c12b-107">在 Visual Basic 中，如果设置为非空值类型的变量`Nothing`，变量设置为其声明的类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="0c12b-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="0c12b-108">在C#，如果将分配到非空值类型的变量`null`，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="0c12b-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c12b-109">备注</span><span class="sxs-lookup"><span data-stu-id="0c12b-109">Remarks</span></span>  
 <span data-ttu-id="0c12b-110">`Nothing` 表示一种数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="0c12b-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="0c12b-111">默认值取决于该变量是值类型的类型或引用类型。</span><span class="sxs-lookup"><span data-stu-id="0c12b-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="0c12b-112">变量*值类型*直接包含它的值。</span><span class="sxs-lookup"><span data-stu-id="0c12b-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="0c12b-113">值类型包括所有数值数据类型， `Boolean`， `Char`， `Date`，所有结构和所有枚举。</span><span class="sxs-lookup"><span data-stu-id="0c12b-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="0c12b-114">变量*引用类型*在内存中存储对对象的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="0c12b-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="0c12b-115">引用类型包括类、 数组、 委托，以及字符串。</span><span class="sxs-lookup"><span data-stu-id="0c12b-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="0c12b-116">有关更多信息，请参见 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0c12b-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="0c12b-117">如果变量是值类型的行为`Nothing`取决于该变量是可以为 null 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0c12b-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="0c12b-118">若要表示为空值类型，将添加`?`修饰符的类型名称。</span><span class="sxs-lookup"><span data-stu-id="0c12b-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="0c12b-119">将分配`Nothing`给可以为 null 的变量的值设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="0c12b-120">有关详细信息和示例，请参阅[可以为 Null 的值类型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="0c12b-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="0c12b-121">如果变量是不可为 null 的值类型，分配给`Nothing`到它将其设置为默认值为其声明的类型。</span><span class="sxs-lookup"><span data-stu-id="0c12b-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="0c12b-122">如果该类型包含变量的成员，它们都设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="0c12b-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="0c12b-123">下面的示例阐释了这一点对于标量类型。</span><span class="sxs-lookup"><span data-stu-id="0c12b-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 <span data-ttu-id="0c12b-124">如果引用类型的变量，将分配`Nothing`为该变量设置它为`null`变量的类型的引用。</span><span class="sxs-lookup"><span data-stu-id="0c12b-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="0c12b-125">设置为一个变量`null`引用不与任何对象相关联。</span><span class="sxs-lookup"><span data-stu-id="0c12b-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="0c12b-126">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="0c12b-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 <span data-ttu-id="0c12b-127">检查变量是否引用 （或可以为 null 的值类型） 时`null`，请不要使用`= Nothing`或`<> Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="0c12b-128">始终使用`Is Nothing`或`IsNot Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="0c12b-129">对于在 Visual Basic 中的字符串，则为空字符串等于`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="0c12b-130">因此，`"" = Nothing`为 true。</span><span class="sxs-lookup"><span data-stu-id="0c12b-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="0c12b-131">下面的示例演示使用的比较`Is`和`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="0c12b-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 <span data-ttu-id="0c12b-132">如果不使用声明一个变量`As`子句并将其设置为`Nothing`，该变量的类型为`Object`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="0c12b-133">此示例是`Dim something = Nothing`。</span><span class="sxs-lookup"><span data-stu-id="0c12b-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="0c12b-134">在这种情况下发生编译时错误时`Option Strict`位于和`Option Infer`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="0c12b-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="0c12b-135">在分配`Nothing`给对象变量，它不再引用任何对象实例。</span><span class="sxs-lookup"><span data-stu-id="0c12b-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="0c12b-136">如果对象之前引用了一个实例，则将其设置为`Nothing`不会终止该实例本身。</span><span class="sxs-lookup"><span data-stu-id="0c12b-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="0c12b-137">终止该实例，并释放与之关联的内存和系统资源，只有在垃圾回收器 (GC) 检测到有任何活动的引用后。</span><span class="sxs-lookup"><span data-stu-id="0c12b-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="0c12b-138">`Nothing` 不同于<xref:System.DBNull>对象，表示未初始化的变量或不存在的数据库列。</span><span class="sxs-lookup"><span data-stu-id="0c12b-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c12b-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c12b-139">See also</span></span>
- [<span data-ttu-id="0c12b-140">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="0c12b-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="0c12b-141">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="0c12b-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="0c12b-142">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="0c12b-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="0c12b-143">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="0c12b-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="0c12b-144">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="0c12b-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="0c12b-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="0c12b-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
