---
title: Set 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349559"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="fcc97-102">Set 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcc97-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="fcc97-103">声明一个 `Set` 属性过程，该过程用于为属性赋值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc97-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcc97-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="fcc97-105">部件</span><span class="sxs-lookup"><span data-stu-id="fcc97-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="fcc97-106">可选。</span><span class="sxs-lookup"><span data-stu-id="fcc97-106">Optional.</span></span> <span data-ttu-id="fcc97-107">请参阅[特性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc97-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="fcc97-108">在此属性中的最多一个 `Get` 和 `Set` 语句上是可选的。</span><span class="sxs-lookup"><span data-stu-id="fcc97-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="fcc97-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="fcc97-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="fcc97-110">Protected</span><span class="sxs-lookup"><span data-stu-id="fcc97-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="fcc97-111">Friend</span><span class="sxs-lookup"><span data-stu-id="fcc97-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="fcc97-112">Private</span><span class="sxs-lookup"><span data-stu-id="fcc97-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="fcc97-113">请参阅 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="fcc97-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="fcc97-114">必需。</span><span class="sxs-lookup"><span data-stu-id="fcc97-114">Required.</span></span> <span data-ttu-id="fcc97-115">包含属性新值的参数。</span><span class="sxs-lookup"><span data-stu-id="fcc97-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="fcc97-116">如果 `Option Strict` `On`，则为必需。</span><span class="sxs-lookup"><span data-stu-id="fcc97-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="fcc97-117">`value` 参数的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fcc97-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="fcc97-118">指定的数据类型必须与声明此 `Set` 语句的属性的数据类型相同。</span><span class="sxs-lookup"><span data-stu-id="fcc97-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="fcc97-119">可选。</span><span class="sxs-lookup"><span data-stu-id="fcc97-119">Optional.</span></span> <span data-ttu-id="fcc97-120">调用 `Set` 属性过程时运行的一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="fcc97-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="fcc97-121">必需。</span><span class="sxs-lookup"><span data-stu-id="fcc97-121">Required.</span></span> <span data-ttu-id="fcc97-122">终止 `Set` 属性过程的定义。</span><span class="sxs-lookup"><span data-stu-id="fcc97-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcc97-123">备注</span><span class="sxs-lookup"><span data-stu-id="fcc97-123">Remarks</span></span>  
 <span data-ttu-id="fcc97-124">每个属性都必须具有 `Set` 属性过程，除非该属性被标记为 `ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="fcc97-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="fcc97-125">`Set` 过程用于设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="fcc97-126">当赋值语句提供要存储在属性中的值时，Visual Basic 会自动调用属性的 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="fcc97-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="fcc97-127">Visual Basic 在属性赋值期间将参数传递给 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="fcc97-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="fcc97-128">如果没有为 `Set`提供参数，集成开发环境（IDE）将使用名为 `value`的隐式参数。</span><span class="sxs-lookup"><span data-stu-id="fcc97-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="fcc97-129">参数保留要赋给属性的值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="fcc97-130">通常将此值存储在私有本地变量中，并在调用 `Get` 过程时返回此值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="fcc97-131">属性声明的主体只能包含属性的 `Get`，并在[Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)和 `End Property` 语句之间包含 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="fcc97-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="fcc97-132">它无法存储这些过程以外的任何内容。</span><span class="sxs-lookup"><span data-stu-id="fcc97-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="fcc97-133">特别是，它无法存储属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="fcc97-134">您必须将此值存储在属性的外部，因为如果将其存储在任一属性过程中，则其他属性过程将无法访问它。</span><span class="sxs-lookup"><span data-stu-id="fcc97-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="fcc97-135">常见的方法是将值存储在与属性在同一级别上声明的[私有](../../../visual-basic/language-reference/modifiers/private.md)变量中。</span><span class="sxs-lookup"><span data-stu-id="fcc97-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="fcc97-136">必须在应用的属性中定义 `Set` 过程。</span><span class="sxs-lookup"><span data-stu-id="fcc97-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="fcc97-137">除非在 `Set` 语句中使用 `accessmodifier`，否则 `Set` 过程默认为其包含属性的访问级别。</span><span class="sxs-lookup"><span data-stu-id="fcc97-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="fcc97-138">规则</span><span class="sxs-lookup"><span data-stu-id="fcc97-138">Rules</span></span>  
  
- <span data-ttu-id="fcc97-139">**混合访问级别。**</span><span class="sxs-lookup"><span data-stu-id="fcc97-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="fcc97-140">如果要定义读写属性，则可以选择为 `Get` 或 `Set` 过程指定不同的访问级别，但不能同时指定两者。</span><span class="sxs-lookup"><span data-stu-id="fcc97-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="fcc97-141">如果执行此操作，则过程访问级别必须比属性的访问级别更严格。</span><span class="sxs-lookup"><span data-stu-id="fcc97-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="fcc97-142">例如，如果属性已 `Friend`声明，则可以将 `Set` 过程声明 `Private`但不 `Public`。</span><span class="sxs-lookup"><span data-stu-id="fcc97-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="fcc97-143">如果正在定义 `WriteOnly` 属性，则 `Set` 过程表示整个属性。</span><span class="sxs-lookup"><span data-stu-id="fcc97-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="fcc97-144">不能为 `Set`声明不同的访问级别，因为这会为属性设置两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="fcc97-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="fcc97-145">行为</span><span class="sxs-lookup"><span data-stu-id="fcc97-145">Behavior</span></span>  
  
- <span data-ttu-id="fcc97-146">**从属性过程返回。**</span><span class="sxs-lookup"><span data-stu-id="fcc97-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="fcc97-147">当 `Set` 过程返回到调用代码时，执行将继续执行提供要存储的值的语句之后。</span><span class="sxs-lookup"><span data-stu-id="fcc97-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="fcc97-148">`Set` 属性过程可以使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或[Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)返回。</span><span class="sxs-lookup"><span data-stu-id="fcc97-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="fcc97-149">`Exit Property` 和 `Return` 语句导致直接从属性过程退出。</span><span class="sxs-lookup"><span data-stu-id="fcc97-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="fcc97-150">任意数量的 `Exit Property` 和 `Return` 语句可以出现在过程中的任何位置，并且可以混合 `Exit Property` 和 `Return` 语句。</span><span class="sxs-lookup"><span data-stu-id="fcc97-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc97-151">示例</span><span class="sxs-lookup"><span data-stu-id="fcc97-151">Example</span></span>  
 <span data-ttu-id="fcc97-152">下面的示例使用 `Set` 语句设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="fcc97-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="fcc97-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fcc97-153">See also</span></span>

- [<span data-ttu-id="fcc97-154">Get 语句</span><span class="sxs-lookup"><span data-stu-id="fcc97-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="fcc97-155">Property 语句</span><span class="sxs-lookup"><span data-stu-id="fcc97-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="fcc97-156">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="fcc97-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="fcc97-157">属性过程</span><span class="sxs-lookup"><span data-stu-id="fcc97-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
