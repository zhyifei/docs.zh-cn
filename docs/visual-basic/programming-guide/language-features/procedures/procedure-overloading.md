---
title: 过程重载 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="ecab7-102">过程重载 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecab7-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="ecab7-103">*重载*过程意味着在多个版本，使用相同名称但不同的参数列表中定义它。</span><span class="sxs-lookup"><span data-stu-id="ecab7-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="ecab7-104">重载的目的是定义过程的几个密切相关的版本，而无需将它们按名称区分开来。</span><span class="sxs-lookup"><span data-stu-id="ecab7-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="ecab7-105">通过不同的参数列表来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="ecab7-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="ecab7-106">重载规则</span><span class="sxs-lookup"><span data-stu-id="ecab7-106">Overloading Rules</span></span>  
 <span data-ttu-id="ecab7-107">重载过程，适用以下规则：</span><span class="sxs-lookup"><span data-stu-id="ecab7-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="ecab7-108">**相同的名称**。</span><span class="sxs-lookup"><span data-stu-id="ecab7-108">**Same Name**.</span></span> <span data-ttu-id="ecab7-109">每个重载的版本必须使用相同的过程名称。</span><span class="sxs-lookup"><span data-stu-id="ecab7-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="ecab7-110">**不同的签名**。</span><span class="sxs-lookup"><span data-stu-id="ecab7-110">**Different Signature**.</span></span> <span data-ttu-id="ecab7-111">每个重载的版本必须不同于在至少一个以下方面的所有其他重载版本：</span><span class="sxs-lookup"><span data-stu-id="ecab7-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="ecab7-112">参数数目</span><span class="sxs-lookup"><span data-stu-id="ecab7-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="ecab7-113">参数的顺序</span><span class="sxs-lookup"><span data-stu-id="ecab7-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="ecab7-114">参数数据类型</span><span class="sxs-lookup"><span data-stu-id="ecab7-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="ecab7-115">类型参数 （对于泛型过程） 数</span><span class="sxs-lookup"><span data-stu-id="ecab7-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="ecab7-116">返回类型 （仅针对转换运算符）</span><span class="sxs-lookup"><span data-stu-id="ecab7-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="ecab7-117">过程名称，以及统称为前述各项*签名*的过程。</span><span class="sxs-lookup"><span data-stu-id="ecab7-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="ecab7-118">当调用重载的过程时，编译器将使用签名来检查调用正确与定义相匹配。</span><span class="sxs-lookup"><span data-stu-id="ecab7-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="ecab7-119">**项不是签名的一部分**。</span><span class="sxs-lookup"><span data-stu-id="ecab7-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="ecab7-120">如果不改变签名，不能重载过程。</span><span class="sxs-lookup"><span data-stu-id="ecab7-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="ecab7-121">具体而言，不能通过一个或多个以下各项仅改变重载过程：</span><span class="sxs-lookup"><span data-stu-id="ecab7-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="ecab7-122">过程修饰符关键字，如`Public`， `Shared`，和 `Static`</span><span class="sxs-lookup"><span data-stu-id="ecab7-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="ecab7-123">参数或类型参数名称</span><span class="sxs-lookup"><span data-stu-id="ecab7-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="ecab7-124">类型参数约束 （针对泛型过程）</span><span class="sxs-lookup"><span data-stu-id="ecab7-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="ecab7-125">参数修饰符关键字，如`ByRef`和 `Optional`</span><span class="sxs-lookup"><span data-stu-id="ecab7-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="ecab7-126">它是否返回一个值</span><span class="sxs-lookup"><span data-stu-id="ecab7-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="ecab7-127">数据类型 （除转换运算符） 的返回值</span><span class="sxs-lookup"><span data-stu-id="ecab7-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="ecab7-128">上面的列表中的项不签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="ecab7-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="ecab7-129">但不能使用它们来区分重载版本，你可以通过它们的签名区分正确的重载版本中对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="ecab7-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="ecab7-130">**后期绑定自变量**。</span><span class="sxs-lookup"><span data-stu-id="ecab7-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="ecab7-131">如果你想要将后期绑定的对象变量传递到重载版本，你必须声明为适当的参数<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="ecab7-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="ecab7-132">过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="ecab7-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="ecab7-133">假设你正在编写`Sub`过程针对客户的平衡，和你发送一个事务想要能够按名称或帐户号，请参阅客户。</span><span class="sxs-lookup"><span data-stu-id="ecab7-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="ecab7-134">若要适应这种情况，可以定义两个不同`Sub`过程，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="ecab7-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="ecab7-135">重载的版本</span><span class="sxs-lookup"><span data-stu-id="ecab7-135">Overloaded Versions</span></span>  
 <span data-ttu-id="ecab7-136">一种替代方法是重载的单一过程名称。</span><span class="sxs-lookup"><span data-stu-id="ecab7-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="ecab7-137">你可以使用[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字来定义为每个参数列表中，过程的一个版本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ecab7-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="ecab7-138">其他重载</span><span class="sxs-lookup"><span data-stu-id="ecab7-138">Additional Overloads</span></span>  
 <span data-ttu-id="ecab7-139">如果你还想要接受在事务量`Decimal`或`Single`，可进一步重载`post`以允许这种变化形式。</span><span class="sxs-lookup"><span data-stu-id="ecab7-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="ecab7-140">如果你这样做这到每个前面的示例中的重载，你会有四个`Sub`过程，它们具有相同名称但具有四个不同的签名。</span><span class="sxs-lookup"><span data-stu-id="ecab7-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="ecab7-141">重载的优点</span><span class="sxs-lookup"><span data-stu-id="ecab7-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="ecab7-142">重载过程的优点是在调用的灵活性。</span><span class="sxs-lookup"><span data-stu-id="ecab7-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="ecab7-143">若要使用`post`过程，声明在前面的示例中，调用代码可以获取的客户标识为`String`或`Integer`，然后在任一情况下调用相同的过程。</span><span class="sxs-lookup"><span data-stu-id="ecab7-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="ecab7-144">下面的示例阐释了这一点：</span><span class="sxs-lookup"><span data-stu-id="ecab7-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ecab7-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecab7-145">See Also</span></span>  
 [<span data-ttu-id="ecab7-146">过程</span><span class="sxs-lookup"><span data-stu-id="ecab7-146">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="ecab7-147">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="ecab7-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="ecab7-148">如何：调用重载过程</span><span class="sxs-lookup"><span data-stu-id="ecab7-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="ecab7-149">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="ecab7-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="ecab7-150">如何：重载参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="ecab7-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="ecab7-151">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="ecab7-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="ecab7-152">重载决策</span><span class="sxs-lookup"><span data-stu-id="ecab7-152">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="ecab7-153">重载</span><span class="sxs-lookup"><span data-stu-id="ecab7-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [<span data-ttu-id="ecab7-154">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="ecab7-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
