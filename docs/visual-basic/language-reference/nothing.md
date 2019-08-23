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
ms.openlocfilehash: 12c88db49dc7723fc269195e7d174bfa822c64d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963751"
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="42d08-102">Nothing (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="42d08-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="42d08-103">表示任意数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="42d08-103">Represents the default value of any data type.</span></span> <span data-ttu-id="42d08-104">对于引用类型, 默认值为`null`引用。</span><span class="sxs-lookup"><span data-stu-id="42d08-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="42d08-105">对于值类型, 默认值取决于值类型是否可以为 null。</span><span class="sxs-lookup"><span data-stu-id="42d08-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42d08-106">对于不可为 null 的值类型`Nothing` , Visual Basic 中的`null`不同C#于中的。</span><span class="sxs-lookup"><span data-stu-id="42d08-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="42d08-107">在 Visual Basic 中, 如果将不可以为 null 的值类型的变量设置`Nothing`为, 则该变量将设置为其声明的类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="42d08-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="42d08-108">在C#中, 如果将不可以为 null 的值类型的变量分配`null`给, 则会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="42d08-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42d08-109">备注</span><span class="sxs-lookup"><span data-stu-id="42d08-109">Remarks</span></span>  
 <span data-ttu-id="42d08-110">`Nothing`表示数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="42d08-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="42d08-111">默认值取决于变量是值类型还是引用类型。</span><span class="sxs-lookup"><span data-stu-id="42d08-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="42d08-112">*值类型*的变量直接包含其值。</span><span class="sxs-lookup"><span data-stu-id="42d08-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="42d08-113">值类型包括所有数值数据类型、 `Boolean`、 `Char`、 `Date`、所有结构和所有枚举。</span><span class="sxs-lookup"><span data-stu-id="42d08-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="42d08-114">*引用类型*的变量存储对内存中对象的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="42d08-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="42d08-115">引用类型包括类、数组、委托和字符串。</span><span class="sxs-lookup"><span data-stu-id="42d08-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="42d08-116">有关更多信息，请参见 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)。</span><span class="sxs-lookup"><span data-stu-id="42d08-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="42d08-117">如果变量是值类型, 则的行为`Nothing`取决于变量是否为可为 null 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="42d08-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="42d08-118">若要表示可以为 null 的值类型`?` , 请向类型名称添加修饰符。</span><span class="sxs-lookup"><span data-stu-id="42d08-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="42d08-119">分配`Nothing`给可以为 null 的变量会将`null`值设置为。</span><span class="sxs-lookup"><span data-stu-id="42d08-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="42d08-120">有关详细信息和示例, 请参阅[可以为 null 的值类型](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)。</span><span class="sxs-lookup"><span data-stu-id="42d08-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="42d08-121">如果变量是不可为 null 的值类型, 则分配`Nothing`给它会将它设置为其声明类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="42d08-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="42d08-122">如果该类型包含变量成员, 则它们都设置为其默认值。</span><span class="sxs-lookup"><span data-stu-id="42d08-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="42d08-123">下面的示例对标量类型进行了说明。</span><span class="sxs-lookup"><span data-stu-id="42d08-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class2.vb#7)]  
  
 <span data-ttu-id="42d08-124">如果变量为引用类型, 则为变量赋值`Nothing`会将其设置`null`为变量类型的引用。</span><span class="sxs-lookup"><span data-stu-id="42d08-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="42d08-125">设置为`null`引用的变量不与任何对象关联。</span><span class="sxs-lookup"><span data-stu-id="42d08-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="42d08-126">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="42d08-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class3.vb#8)]  
  
 <span data-ttu-id="42d08-127">当检查引用 (或可以为 null 的值类型) 变量`null`是否为时, `= Nothing`请`<> Nothing`不要使用或。</span><span class="sxs-lookup"><span data-stu-id="42d08-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="42d08-128">始终使用`Is Nothing`或`IsNot Nothing`。</span><span class="sxs-lookup"><span data-stu-id="42d08-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="42d08-129">对于 Visual Basic 中的字符串, 空字符串等于`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="42d08-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="42d08-130">因此, `"" = Nothing`为 true。</span><span class="sxs-lookup"><span data-stu-id="42d08-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="42d08-131">下面的示例演示使用`Is`和`IsNot`运算符的比较。</span><span class="sxs-lookup"><span data-stu-id="42d08-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class4.vb#9)]  
  
 <span data-ttu-id="42d08-132">如果在不使用`As`子句的情况下声明变量并将其设置为`Nothing`, 则该`Object`变量的类型为。</span><span class="sxs-lookup"><span data-stu-id="42d08-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="42d08-133">这是`Dim something = Nothing`一个示例。</span><span class="sxs-lookup"><span data-stu-id="42d08-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="42d08-134">当处于打开状态且处于关闭状态时`Option Strict` , `Option Infer`会发生编译时错误。</span><span class="sxs-lookup"><span data-stu-id="42d08-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="42d08-135">将分配`Nothing`给对象变量时, 它将不再引用任何对象实例。</span><span class="sxs-lookup"><span data-stu-id="42d08-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="42d08-136">如果变量以前引用了某个实例, 则将其设置为`Nothing`不会终止实例本身。</span><span class="sxs-lookup"><span data-stu-id="42d08-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="42d08-137">实例终止, 仅在垃圾回收器 (GC) 检测到没有剩余活动引用时, 才会释放与之关联的内存和系统资源。</span><span class="sxs-lookup"><span data-stu-id="42d08-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="42d08-138">`Nothing`<xref:System.DBNull>与对象不同, 后者表示未初始化的变量或不存在的数据库列。</span><span class="sxs-lookup"><span data-stu-id="42d08-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d08-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="42d08-139">See also</span></span>

- [<span data-ttu-id="42d08-140">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="42d08-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="42d08-141">对象生存期:如何创建和销毁对象</span><span class="sxs-lookup"><span data-stu-id="42d08-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [<span data-ttu-id="42d08-142">生存期 (Visual Basic</span><span class="sxs-lookup"><span data-stu-id="42d08-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="42d08-143">Is 运算符</span><span class="sxs-lookup"><span data-stu-id="42d08-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="42d08-144">IsNot 运算符</span><span class="sxs-lookup"><span data-stu-id="42d08-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="42d08-145">可以为 null 的值类型</span><span class="sxs-lookup"><span data-stu-id="42d08-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
