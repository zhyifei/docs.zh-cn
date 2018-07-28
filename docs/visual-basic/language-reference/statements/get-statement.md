---
title: Get 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 32b89caf56c010f9e6ed7b78309ef30b56b682ea
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332891"
---
# <a name="get-statement"></a><span data-ttu-id="de897-102">Get 语句</span><span class="sxs-lookup"><span data-stu-id="de897-102">Get Statement</span></span>
<span data-ttu-id="de897-103">声明`Get`用于检索属性值的属性过程。</span><span class="sxs-lookup"><span data-stu-id="de897-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de897-104">语法</span><span class="sxs-lookup"><span data-stu-id="de897-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="de897-105">部件</span><span class="sxs-lookup"><span data-stu-id="de897-105">Parts</span></span>  
  
|<span data-ttu-id="de897-106">术语</span><span class="sxs-lookup"><span data-stu-id="de897-106">Term</span></span>|<span data-ttu-id="de897-107">定义</span><span class="sxs-lookup"><span data-stu-id="de897-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="de897-108">可选。</span><span class="sxs-lookup"><span data-stu-id="de897-108">Optional.</span></span> <span data-ttu-id="de897-109">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="de897-109">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="de897-110">在最多一个的可选`Get`和`Set`中此属性的语句。</span><span class="sxs-lookup"><span data-stu-id="de897-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="de897-111">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="de897-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="de897-112">-   [受保护](../../../visual-basic/language-reference/modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="de897-112">-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)</span></span><br /><span data-ttu-id="de897-113">-   [友元](../../../visual-basic/language-reference/modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="de897-113">-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)</span></span><br /><span data-ttu-id="de897-114">-   [专用](../../../visual-basic/language-reference/modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="de897-114">-   [Private](../../../visual-basic/language-reference/modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="de897-115">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="de897-115">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="de897-116">可选。</span><span class="sxs-lookup"><span data-stu-id="de897-116">Optional.</span></span> <span data-ttu-id="de897-117">运行时的一个或多个语句`Get`调用属性过程。</span><span class="sxs-lookup"><span data-stu-id="de897-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="de897-118">必须的。</span><span class="sxs-lookup"><span data-stu-id="de897-118">Required.</span></span> <span data-ttu-id="de897-119">终止的定义`Get`属性过程。</span><span class="sxs-lookup"><span data-stu-id="de897-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de897-120">备注</span><span class="sxs-lookup"><span data-stu-id="de897-120">Remarks</span></span>  
 <span data-ttu-id="de897-121">每个属性必须具有`Get`属性过程除非该属性标记为`WriteOnly`。</span><span class="sxs-lookup"><span data-stu-id="de897-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="de897-122">`Get`过程用于返回属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="de897-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="de897-123">Visual Basic 会自动调用属性的`Get`表达式请求属性的值时的过程。</span><span class="sxs-lookup"><span data-stu-id="de897-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="de897-124">属性声明的主体可以包含仅属性的`Get`并`Set`过程之间[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="de897-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="de897-125">它不能存储这些过程之外的任何内容。</span><span class="sxs-lookup"><span data-stu-id="de897-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="de897-126">具体而言，它不能存储属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="de897-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="de897-127">必须存储属性，超出此值，因为如果将其存储在属性过程之一，另一个属性过程不能访问它。</span><span class="sxs-lookup"><span data-stu-id="de897-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="de897-128">常用方法是存储中的值[专用](../../../visual-basic/language-reference/modifiers/private.md)变量声明为属性的级别相同。</span><span class="sxs-lookup"><span data-stu-id="de897-128">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="de897-129">必须定义`Get`它所应用于的属性内的过程。</span><span class="sxs-lookup"><span data-stu-id="de897-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="de897-130">`Get`过程默认为其包含的属性的访问级别，除非使用`accessmodifier`中`Get`语句。</span><span class="sxs-lookup"><span data-stu-id="de897-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="de897-131">规则</span><span class="sxs-lookup"><span data-stu-id="de897-131">Rules</span></span>  
  
-   <span data-ttu-id="de897-132">**混合的访问级别。**</span><span class="sxs-lookup"><span data-stu-id="de897-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="de897-133">如果你正在定义的读-写属性，您可以选择指定不同的访问级别为`Get`或`Set`过程，但不可同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="de897-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="de897-134">如果执行此操作时，过程访问级别必须比属性的访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="de897-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="de897-135">例如，如果属性声明`Friend`，可以声明`Get`过程`Private`，但不是`Public`。</span><span class="sxs-lookup"><span data-stu-id="de897-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="de897-136">如果您要定义`ReadOnly`属性，`Get`过程都表示整个属性。</span><span class="sxs-lookup"><span data-stu-id="de897-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="de897-137">不能声明不同的访问级别`Get`，因为这会设置属性的两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="de897-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="de897-138">**返回类型。**</span><span class="sxs-lookup"><span data-stu-id="de897-138">**Return Type.**</span></span> <span data-ttu-id="de897-139">[Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)可以声明其返回的值的数据类型。</span><span class="sxs-lookup"><span data-stu-id="de897-139">The [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="de897-140">`Get`过程会自动返回数据类型。</span><span class="sxs-lookup"><span data-stu-id="de897-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="de897-141">您可以指定任何数据类型或枚举、 结构、 类或接口的名称。</span><span class="sxs-lookup"><span data-stu-id="de897-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="de897-142">如果`Property`语句不指定`returntype`，该过程返回`Object`。</span><span class="sxs-lookup"><span data-stu-id="de897-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="de897-143">行为</span><span class="sxs-lookup"><span data-stu-id="de897-143">Behavior</span></span>  
  
-   <span data-ttu-id="de897-144">**从过程中返回。**</span><span class="sxs-lookup"><span data-stu-id="de897-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="de897-145">当`Get`过程返回到调用代码，请求的属性值的语句中将继续执行。</span><span class="sxs-lookup"><span data-stu-id="de897-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="de897-146">`Get` 属性过程可以返回值使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或者将返回值分配给属性名称。</span><span class="sxs-lookup"><span data-stu-id="de897-146">`Get` property procedures can return a value using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="de897-147">详细信息，请参阅"返回值"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="de897-147">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="de897-148">`Exit Property`和`Return`语句从属性过程会导致立即退出。</span><span class="sxs-lookup"><span data-stu-id="de897-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="de897-149">任意数量的`Exit Property`并`Return`语句可以在过程中，任何位置出现，并且可以混合`Exit Property`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="de897-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="de897-150">**返回值。**</span><span class="sxs-lookup"><span data-stu-id="de897-150">**Return Value.**</span></span> <span data-ttu-id="de897-151">若要返回的值`Get`过程中，可以将值分配给属性名称或将其包含在[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="de897-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span> <span data-ttu-id="de897-152">`Return`语句将同时分配`Get`过程返回值，并退出该过程。</span><span class="sxs-lookup"><span data-stu-id="de897-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="de897-153">如果您使用`Exit Property`而不将值分配到的属性名`Get`过程将返回属性的数据类型的默认值。</span><span class="sxs-lookup"><span data-stu-id="de897-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="de897-154">详细信息，请参阅"返回值"中[Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="de897-154">For more information, see "Return Value" in [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
     <span data-ttu-id="de897-155">下面的示例演示两种方法的只读属性`quoteForTheDay`可保存在私有变量的值返回`quoteValue`。</span><span class="sxs-lookup"><span data-stu-id="de897-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="de897-156">示例</span><span class="sxs-lookup"><span data-stu-id="de897-156">Example</span></span>  
 <span data-ttu-id="de897-157">下面的示例使用`Get`语句返回的属性值。</span><span class="sxs-lookup"><span data-stu-id="de897-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="de897-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="de897-158">See Also</span></span>  
 [<span data-ttu-id="de897-159">Set 语句</span><span class="sxs-lookup"><span data-stu-id="de897-159">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="de897-160">Property 语句</span><span class="sxs-lookup"><span data-stu-id="de897-160">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="de897-161">Exit 语句</span><span class="sxs-lookup"><span data-stu-id="de897-161">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="de897-162">对象和类</span><span class="sxs-lookup"><span data-stu-id="de897-162">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="de897-163">演练：定义类</span><span class="sxs-lookup"><span data-stu-id="de897-163">Walkthrough: Defining Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
