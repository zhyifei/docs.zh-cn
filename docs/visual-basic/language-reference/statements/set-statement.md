---
title: "Set 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b18e6c858e64e78d7ab85fdaafd70e510f7a02f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="c41fa-102">Set 语句 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c41fa-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="c41fa-103">声明`Set`用于将值分配给属性的属性过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c41fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="c41fa-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="c41fa-105">部件</span><span class="sxs-lookup"><span data-stu-id="c41fa-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="c41fa-106">可选。</span><span class="sxs-lookup"><span data-stu-id="c41fa-106">Optional.</span></span> <span data-ttu-id="c41fa-107">请参阅[属性列表](../../../visual-basic/language-reference/statements/attribute-list.md)。</span><span class="sxs-lookup"><span data-stu-id="c41fa-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="c41fa-108">在最多一种可选`Get`和`Set`此属性中的语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="c41fa-109">可以是以下各项之一：</span><span class="sxs-lookup"><span data-stu-id="c41fa-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="c41fa-110">Protected</span><span class="sxs-lookup"><span data-stu-id="c41fa-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="c41fa-111">Friend</span><span class="sxs-lookup"><span data-stu-id="c41fa-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="c41fa-112">Private</span><span class="sxs-lookup"><span data-stu-id="c41fa-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="c41fa-113">请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="c41fa-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="c41fa-114">必需。</span><span class="sxs-lookup"><span data-stu-id="c41fa-114">Required.</span></span> <span data-ttu-id="c41fa-115">参数，其中包含属性的新值。</span><span class="sxs-lookup"><span data-stu-id="c41fa-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="c41fa-116">如果存在`Option Strict`是`On`。</span><span class="sxs-lookup"><span data-stu-id="c41fa-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="c41fa-117">数据类型的`value`参数。</span><span class="sxs-lookup"><span data-stu-id="c41fa-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="c41fa-118">指定的数据类型必须是属性的数据类型相同，这`Set`声明语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="c41fa-119">可选。</span><span class="sxs-lookup"><span data-stu-id="c41fa-119">Optional.</span></span> <span data-ttu-id="c41fa-120">运行时的一个或多个语句`Set`调用属性过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="c41fa-121">必需。</span><span class="sxs-lookup"><span data-stu-id="c41fa-121">Required.</span></span> <span data-ttu-id="c41fa-122">终止的定义`Set`属性过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c41fa-123">备注</span><span class="sxs-lookup"><span data-stu-id="c41fa-123">Remarks</span></span>  
 <span data-ttu-id="c41fa-124">每个属性必须具有`Set`属性过程除非该属性被标记为`ReadOnly`。</span><span class="sxs-lookup"><span data-stu-id="c41fa-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="c41fa-125">`Set`过程用于设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="c41fa-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="c41fa-126">Visual Basic 将自动调用属性的`Set`在赋值语句将提供一个值，以在属性中存储的过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="c41fa-127">Visual Basic 将传递到参数`Set`属性分配期间的过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="c41fa-128">如果未提供的参数`Set`，集成的开发环境 (IDE) 使用名为的隐式参数`value`。</span><span class="sxs-lookup"><span data-stu-id="c41fa-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="c41fa-129">参数包含要分配给属性的值。</span><span class="sxs-lookup"><span data-stu-id="c41fa-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="c41fa-130">通常将此值存储在专用的本地变量，并将其返回每当`Get`调用过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="c41fa-131">属性声明的主体可以包含仅属性的`Get`和`Set`之间过程[属性语句](../../../visual-basic/language-reference/statements/property-statement.md)和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="c41fa-132">无法将存储这些过程之外的任何内容。</span><span class="sxs-lookup"><span data-stu-id="c41fa-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="c41fa-133">具体而言，它不能存储属性的当前值。</span><span class="sxs-lookup"><span data-stu-id="c41fa-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="c41fa-134">必须存储此值超出了该属性，因为如果将其存储在属性过程之一，另一个属性过程无法访问它。</span><span class="sxs-lookup"><span data-stu-id="c41fa-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="c41fa-135">常用方法是存储中的值[私有](../../../visual-basic/language-reference/modifiers/private.md)作为属性的相同级别声明的变量。</span><span class="sxs-lookup"><span data-stu-id="c41fa-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="c41fa-136">必须定义`Set`所适用的属性的内部过程。</span><span class="sxs-lookup"><span data-stu-id="c41fa-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="c41fa-137">`Set`过程默认为其包含的属性的访问级别，除非使用`accessmodifier`中`Set`语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c41fa-138">规则</span><span class="sxs-lookup"><span data-stu-id="c41fa-138">Rules</span></span>  
  
-   <span data-ttu-id="c41fa-139">**混合的访问级别。**</span><span class="sxs-lookup"><span data-stu-id="c41fa-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="c41fa-140">如果你正在定义一个读 / 写属性，你可以选择指定不同的访问级别也`Get`或`Set`过程中，但不是两者。</span><span class="sxs-lookup"><span data-stu-id="c41fa-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="c41fa-141">如果执行此操作时，过程访问级别必须比属性访问级别限制性更强。</span><span class="sxs-lookup"><span data-stu-id="c41fa-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="c41fa-142">例如，如果属性声明`Friend`，可以声明`Set`过程`Private`，但不是`Public`。</span><span class="sxs-lookup"><span data-stu-id="c41fa-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="c41fa-143">如果你正在定义`WriteOnly`属性，`Set`过程表示整个属性。</span><span class="sxs-lookup"><span data-stu-id="c41fa-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="c41fa-144">你不能声明不同的访问级别`Set`，因为这会设置属性的两个访问级别。</span><span class="sxs-lookup"><span data-stu-id="c41fa-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="c41fa-145">行为</span><span class="sxs-lookup"><span data-stu-id="c41fa-145">Behavior</span></span>  
  
-   <span data-ttu-id="c41fa-146">**返回从属性过程。**</span><span class="sxs-lookup"><span data-stu-id="c41fa-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="c41fa-147">当`Set`过程返回到调用代码时，将会继续执行提供了要存储的值的语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="c41fa-148">`Set`属性过程可以返回使用[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)或[退出语句](../../../visual-basic/language-reference/statements/exit-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="c41fa-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="c41fa-149">`Exit Property`和`Return`语句从属性过程会导致立即退出。</span><span class="sxs-lookup"><span data-stu-id="c41fa-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="c41fa-150">任意数量的`Exit Property`和`Return`语句可以出现的任何位置在过程中，并可混合`Exit Property`和`Return`语句。</span><span class="sxs-lookup"><span data-stu-id="c41fa-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c41fa-151">示例</span><span class="sxs-lookup"><span data-stu-id="c41fa-151">Example</span></span>  
 <span data-ttu-id="c41fa-152">下面的示例使用`Set`语句将设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="c41fa-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c41fa-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c41fa-153">See Also</span></span>  
 [<span data-ttu-id="c41fa-154">Get 语句</span><span class="sxs-lookup"><span data-stu-id="c41fa-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="c41fa-155">Property 语句</span><span class="sxs-lookup"><span data-stu-id="c41fa-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="c41fa-156">Sub 语句</span><span class="sxs-lookup"><span data-stu-id="c41fa-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="c41fa-157">属性过程</span><span class="sxs-lookup"><span data-stu-id="c41fa-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
