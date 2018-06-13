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
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603985"
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="d946c-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d946c-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="d946c-103">表示任何数据类型的默认的值。</span><span class="sxs-lookup"><span data-stu-id="d946c-103">Represents the default value of any data type.</span></span> <span data-ttu-id="d946c-104">对于引用类型，默认值是`null`引用。</span><span class="sxs-lookup"><span data-stu-id="d946c-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="d946c-105">对于值类型，默认值取决于是否可以为 null 的值类型。</span><span class="sxs-lookup"><span data-stu-id="d946c-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d946c-106">对于不可为 null 的值类型，`Nothing`在 Visual Basic 中区别`null`C# 中。</span><span class="sxs-lookup"><span data-stu-id="d946c-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="d946c-107">在 Visual Basic 中，如果设置为不可为 null 的值类型的变量`Nothing`，则变量设置为其声明的类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="d946c-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="d946c-108">在 C# 中，如果将分配到的不可为 null 的值类型的变量`null`，则发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="d946c-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d946c-109">备注</span><span class="sxs-lookup"><span data-stu-id="d946c-109">Remarks</span></span>  
 <span data-ttu-id="d946c-110">`Nothing` 表示一种数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="d946c-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="d946c-111">默认值取决于变量是值类型或引用类型。</span><span class="sxs-lookup"><span data-stu-id="d946c-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="d946c-112">变量*值类型*直接包含其值。</span><span class="sxs-lookup"><span data-stu-id="d946c-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="d946c-113">值类型包括所有数值数据类型， `Boolean`， `Char`， `Date`，所有的结构和所有枚举。</span><span class="sxs-lookup"><span data-stu-id="d946c-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="d946c-114">变量*引用类型*在内存中存储对对象的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="d946c-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="d946c-115">引用类型包括类、 数组、 委托和字符串。</span><span class="sxs-lookup"><span data-stu-id="d946c-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="d946c-116">有关更多信息，请参见 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d946c-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="d946c-117">如果变量是值类型、 的行为`Nothing`取决于变量是否是可以为 null 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="d946c-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="d946c-118">若要表示为 null 的值类型，添加`?`修饰符向类型名称。</span><span class="sxs-lookup"><span data-stu-id="d946c-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="d946c-119">分配`Nothing`为可为 null 的变量将值设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="d946c-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="d946c-120">有关详细信息和示例，请参阅[可以为 Null 的值类型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d946c-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="d946c-121">如果不可以为 null 的值类型的变量，将分配`Nothing`到它将其设置为默认值为其声明的类型。</span><span class="sxs-lookup"><span data-stu-id="d946c-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="d946c-122">如果该类型包含变量的成员，它们都设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="d946c-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="d946c-123">下面的示例阐释了这一点的标量类型。</span><span class="sxs-lookup"><span data-stu-id="d946c-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 <span data-ttu-id="d946c-124">如果变量为引用类型，分配给`Nothing`给该变量请将其设置为`null`变量的类型的引用。</span><span class="sxs-lookup"><span data-stu-id="d946c-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="d946c-125">设置为变量`null`引用不与任何对象相关联。</span><span class="sxs-lookup"><span data-stu-id="d946c-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="d946c-126">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="d946c-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 <span data-ttu-id="d946c-127">检查是否引用 （或可以为 null 的值类型） 变量时`null`，不要使用`= Nothing`或`<> Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d946c-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="d946c-128">始终使用`Is Nothing`或`IsNot Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d946c-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="d946c-129">在 Visual Basic 中的字符串，等于空字符串`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d946c-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="d946c-130">因此，`"" = Nothing`为 true。</span><span class="sxs-lookup"><span data-stu-id="d946c-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="d946c-131">下面的示例演示使用的比较`Is`和`IsNot`运算符。</span><span class="sxs-lookup"><span data-stu-id="d946c-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 <span data-ttu-id="d946c-132">如果您声明一个变量而无需使用`As`子句将其设置为`Nothing`，该变量具有一种`Object`。</span><span class="sxs-lookup"><span data-stu-id="d946c-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="d946c-133">此示例是`Dim something = Nothing`。</span><span class="sxs-lookup"><span data-stu-id="d946c-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="d946c-134">在这种情况下发生编译时错误时`Option Strict`位于和`Option Infer`处于关闭状态。</span><span class="sxs-lookup"><span data-stu-id="d946c-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="d946c-135">当分配`Nothing`给对象变量，它不再引用任何对象实例。</span><span class="sxs-lookup"><span data-stu-id="d946c-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="d946c-136">如果变量具有以前引用了一个实例，则将其设置为`Nothing`不会终止该实例本身。</span><span class="sxs-lookup"><span data-stu-id="d946c-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="d946c-137">终止该实例，并释放与之关联的内存和系统资源，仅后垃圾回收器 (GC) 检测到没有任何活动的引用。</span><span class="sxs-lookup"><span data-stu-id="d946c-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="d946c-138">`Nothing` 不同于<xref:System.DBNull>对象，用于表示未初始化的变量或不存在的数据库列。</span><span class="sxs-lookup"><span data-stu-id="d946c-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d946c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d946c-139">See Also</span></span>  
 [<span data-ttu-id="d946c-140">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="d946c-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="d946c-141">对象生存期：如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="d946c-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="d946c-142">在 Visual Basic 中的生存期</span><span class="sxs-lookup"><span data-stu-id="d946c-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="d946c-143">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="d946c-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="d946c-144">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="d946c-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="d946c-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="d946c-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
