---
title: 如何：创建属性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
ms.openlocfilehash: 6e3faed9880b6417f17ab8fe84bc5162e803c437
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656238"
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="82358-102">如何：创建属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82358-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="82358-103">括起属性定义之间`Property`语句和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="82358-104">在此定义您定义`Get`过程中，`Set`过程中，和/或文件名。</span><span class="sxs-lookup"><span data-stu-id="82358-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="82358-105">该属性的所有代码均位于这些过程内。</span><span class="sxs-lookup"><span data-stu-id="82358-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="82358-106">`Get`过程将检索该属性的值与`Set`过程存储一个值。</span><span class="sxs-lookup"><span data-stu-id="82358-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="82358-107">如果你想要具有读/写访问的属性，则必须定义这两个过程。</span><span class="sxs-lookup"><span data-stu-id="82358-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="82358-108">对于只读属性，只需定义`Get`，并为只写属性，只需定义`Set`。</span><span class="sxs-lookup"><span data-stu-id="82358-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="82358-109">创建一个属性</span><span class="sxs-lookup"><span data-stu-id="82358-109">To create a property</span></span>  
  
1.  <span data-ttu-id="82358-110">在任何属性或过程，之外使用[属性语句](../../../../visual-basic/language-reference/statements/property-statement.md)后, 跟`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="82358-111">如果该属性接受参数，请按照`Property`关键字的过程中，然后在括号中的参数列表的名称。</span><span class="sxs-lookup"><span data-stu-id="82358-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="82358-112">括号后跟`As`子句来指定属性的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="82358-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="82358-113">必须指定即使对于只写属性的数据类型。</span><span class="sxs-lookup"><span data-stu-id="82358-113">You must specify the data type even for a write-only property.</span></span>  
  
4.  <span data-ttu-id="82358-114">添加`Get`和`Set`于相应过程。</span><span class="sxs-lookup"><span data-stu-id="82358-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="82358-115">请参阅下面的说明。</span><span class="sxs-lookup"><span data-stu-id="82358-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="82358-116">若要创建 Get 过程，将检索属性值</span><span class="sxs-lookup"><span data-stu-id="82358-116">To create a Get procedure that retrieves a property value</span></span>  
  
1.  <span data-ttu-id="82358-117">之间`Property`和`End Property`语句，编写[Get 语句](../../../../visual-basic/language-reference/statements/get-statement.md)后, 跟`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="82358-118">不需要定义的任意参数`Get`过程。</span><span class="sxs-lookup"><span data-stu-id="82358-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2.  <span data-ttu-id="82358-119">若要检索的属性的值之间的代码语句放`Get`和`End Get`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="82358-120">此代码还可以包括其他计算和数据操作，除了生成并返回该属性的值。</span><span class="sxs-lookup"><span data-stu-id="82358-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3.  <span data-ttu-id="82358-121">使用`Return`语句返回属性的值返回到调用代码。</span><span class="sxs-lookup"><span data-stu-id="82358-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="82358-122">你必须编写`Get`过程对于读写属性和只读属性。</span><span class="sxs-lookup"><span data-stu-id="82358-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="82358-123">你无需定义`Get`只写属性的过程。</span><span class="sxs-lookup"><span data-stu-id="82358-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="82358-124">若要创建一个组的过程，它将写入属性的值</span><span class="sxs-lookup"><span data-stu-id="82358-124">To create a Set procedure that writes a property's value</span></span>  
  
1.  <span data-ttu-id="82358-125">之间`Property`和`End Property`语句，编写[Set 语句](../../../../visual-basic/language-reference/statements/set-statement.md)后, 跟`End Set`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2.  <span data-ttu-id="82358-126">在`Set`语句，请按照`Set`使用参数列表在括号中的关键字。</span><span class="sxs-lookup"><span data-stu-id="82358-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="82358-127">此参数列表必须包含调用代码传递的值至少值参数。</span><span class="sxs-lookup"><span data-stu-id="82358-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="82358-128">此值参数的默认名称是`Value`，但是如果需要，可以使用其他名称。</span><span class="sxs-lookup"><span data-stu-id="82358-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="82358-129">值参数必须具有相同的数据类型与属性本身。</span><span class="sxs-lookup"><span data-stu-id="82358-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3.  <span data-ttu-id="82358-130">将代码语句之间的属性中存储值放`Set`和`End Set`语句。</span><span class="sxs-lookup"><span data-stu-id="82358-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="82358-131">此代码还可以包括其他计算和除了验证并将该属性的值存储的数据操作。</span><span class="sxs-lookup"><span data-stu-id="82358-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4.  <span data-ttu-id="82358-132">使用 value 参数以接受调用的代码提供的值。</span><span class="sxs-lookup"><span data-stu-id="82358-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="82358-133">可以直接在赋值语句中，存储此值，也可以在表达式中使用计算要存储的内部值。</span><span class="sxs-lookup"><span data-stu-id="82358-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="82358-134">你必须编写`Set`过程对于读写属性和只写属性。</span><span class="sxs-lookup"><span data-stu-id="82358-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="82358-135">你无需定义`Set`只读属性的过程。</span><span class="sxs-lookup"><span data-stu-id="82358-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82358-136">示例</span><span class="sxs-lookup"><span data-stu-id="82358-136">Example</span></span>  
 <span data-ttu-id="82358-137">下面的示例创建一个读/写属性，将为完整的名称存储为两个构成的名称、 名字和姓氏。</span><span class="sxs-lookup"><span data-stu-id="82358-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="82358-138">当调用的代码读取`fullName`、`Get`过程合并两个构成的名称，并返回的完整名称。</span><span class="sxs-lookup"><span data-stu-id="82358-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="82358-139">当调用的代码将分配新的完整名称，`Set`过程尝试将其分解为两个构成的名称。</span><span class="sxs-lookup"><span data-stu-id="82358-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="82358-140">如果找不到空间，它可以将其存储所有项作为第一个名称。</span><span class="sxs-lookup"><span data-stu-id="82358-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 <span data-ttu-id="82358-141">下面的示例演示对属性过程的典型调用`fullName`。</span><span class="sxs-lookup"><span data-stu-id="82358-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="82358-142">第一次调用设置的属性值和第二个调用检索到它。</span><span class="sxs-lookup"><span data-stu-id="82358-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="82358-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="82358-143">See Also</span></span>  
 [<span data-ttu-id="82358-144">过程</span><span class="sxs-lookup"><span data-stu-id="82358-144">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="82358-145">属性过程</span><span class="sxs-lookup"><span data-stu-id="82358-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="82358-146">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="82358-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="82358-147">在 Visual Basic 中属性和变量之间的差异</span><span class="sxs-lookup"><span data-stu-id="82358-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="82358-148">如何：声明具有混合访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="82358-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="82358-149">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="82358-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="82358-150">如何： 声明和 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="82358-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="82358-151">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="82358-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="82358-152">如何：从属性获取值</span><span class="sxs-lookup"><span data-stu-id="82358-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
