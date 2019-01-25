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
ms.openlocfilehash: 3cb11079241da4815c6e7bde4a76123965a95514
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712517"
---
# <a name="procedure-overloading-visual-basic"></a><span data-ttu-id="827a1-102">过程重载 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="827a1-102">Procedure Overloading (Visual Basic)</span></span>
<span data-ttu-id="827a1-103">*重载*过程是指在多个版本中，使用相同名称但不同的参数列表定义。</span><span class="sxs-lookup"><span data-stu-id="827a1-103">*Overloading* a procedure means defining it in multiple versions, using the same name but different parameter lists.</span></span> <span data-ttu-id="827a1-104">重载的目的是定义一个过程的几个密切相关的版本而无需将它们按名称区分开。</span><span class="sxs-lookup"><span data-stu-id="827a1-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span> <span data-ttu-id="827a1-105">通过不同的参数列表执行此操作。</span><span class="sxs-lookup"><span data-stu-id="827a1-105">You do this by varying the parameter list.</span></span>  
  
## <a name="overloading-rules"></a><span data-ttu-id="827a1-106">重载规则</span><span class="sxs-lookup"><span data-stu-id="827a1-106">Overloading Rules</span></span>  
 <span data-ttu-id="827a1-107">当重载的过程时，以下规则适用：</span><span class="sxs-lookup"><span data-stu-id="827a1-107">When you overload a procedure, the following rules apply:</span></span>  
  
-   <span data-ttu-id="827a1-108">**相同的名称**。</span><span class="sxs-lookup"><span data-stu-id="827a1-108">**Same Name**.</span></span> <span data-ttu-id="827a1-109">每个重载的版本必须使用相同的过程名称。</span><span class="sxs-lookup"><span data-stu-id="827a1-109">Each overloaded version must use the same procedure name.</span></span>  
  
-   <span data-ttu-id="827a1-110">**不同的签名**。</span><span class="sxs-lookup"><span data-stu-id="827a1-110">**Different Signature**.</span></span> <span data-ttu-id="827a1-111">每个重载的版本必须不同于至少一个以下方面中的所有其他重载版本：</span><span class="sxs-lookup"><span data-stu-id="827a1-111">Each overloaded version must differ from all other overloaded versions in at least one of the following respects:</span></span>  
  
    -   <span data-ttu-id="827a1-112">参数数目</span><span class="sxs-lookup"><span data-stu-id="827a1-112">Number of parameters</span></span>  
  
    -   <span data-ttu-id="827a1-113">参数的顺序</span><span class="sxs-lookup"><span data-stu-id="827a1-113">Order of the parameters</span></span>  
  
    -   <span data-ttu-id="827a1-114">参数的数据类型</span><span class="sxs-lookup"><span data-stu-id="827a1-114">Data types of the parameters</span></span>  
  
    -   <span data-ttu-id="827a1-115">（针对泛型过程） 的类型参数的数目</span><span class="sxs-lookup"><span data-stu-id="827a1-115">Number of type parameters (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="827a1-116">（仅适用于转换运算符） 的返回类型</span><span class="sxs-lookup"><span data-stu-id="827a1-116">Return type (only for a conversion operator)</span></span>  
  
     <span data-ttu-id="827a1-117">前面的项目统称为过程名称，以及*签名*的过程。</span><span class="sxs-lookup"><span data-stu-id="827a1-117">Together with the procedure name, the preceding items are collectively called the *signature* of the procedure.</span></span> <span data-ttu-id="827a1-118">当您调用重载的过程时，编译器将使用签名来检查在调用与定义正确匹配。</span><span class="sxs-lookup"><span data-stu-id="827a1-118">When you call an overloaded procedure, the compiler uses the signature to check that the call correctly matches the definition.</span></span>  
  
-   <span data-ttu-id="827a1-119">**项不属于签名**。</span><span class="sxs-lookup"><span data-stu-id="827a1-119">**Items Not Part of Signature**.</span></span> <span data-ttu-id="827a1-120">如果不改变签名，不能重载的过程。</span><span class="sxs-lookup"><span data-stu-id="827a1-120">You cannot overload a procedure without varying the signature.</span></span> <span data-ttu-id="827a1-121">具体而言，不能通过只改变一个或多个以下各项的重载的过程：</span><span class="sxs-lookup"><span data-stu-id="827a1-121">In particular, you cannot overload a procedure by varying only one or more of the following items:</span></span>  
  
    -   <span data-ttu-id="827a1-122">过程修饰符关键字，如`Public`， `Shared`，和 `Static`</span><span class="sxs-lookup"><span data-stu-id="827a1-122">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`</span></span>  
  
    -   <span data-ttu-id="827a1-123">参数或类型参数名称</span><span class="sxs-lookup"><span data-stu-id="827a1-123">Parameter or type parameter names</span></span>  
  
    -   <span data-ttu-id="827a1-124">（针对泛型过程） 的类型参数约束</span><span class="sxs-lookup"><span data-stu-id="827a1-124">Type parameter constraints (for a generic procedure)</span></span>  
  
    -   <span data-ttu-id="827a1-125">参数修饰符关键字，如`ByRef`和 `Optional`</span><span class="sxs-lookup"><span data-stu-id="827a1-125">Parameter modifier keywords, such as `ByRef` and `Optional`</span></span>  
  
    -   <span data-ttu-id="827a1-126">它是否返回一个值</span><span class="sxs-lookup"><span data-stu-id="827a1-126">Whether it returns a value</span></span>  
  
    -   <span data-ttu-id="827a1-127">（除转换运算符） 的返回值数据类型</span><span class="sxs-lookup"><span data-stu-id="827a1-127">The data type of the return value (except for a conversion operator)</span></span>  
  
     <span data-ttu-id="827a1-128">前面列表中的项不是签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="827a1-128">The items in the preceding list are not part of the signature.</span></span> <span data-ttu-id="827a1-129">虽然不能使用它们来区分重载版本，您可以更改它们之间按它们的签名正确区分的重载版本。</span><span class="sxs-lookup"><span data-stu-id="827a1-129">Although you cannot use them to differentiate between overloaded versions, you can vary them among overloaded versions that are properly differentiated by their signatures.</span></span>  
  
-   <span data-ttu-id="827a1-130">**后期绑定的参数**。</span><span class="sxs-lookup"><span data-stu-id="827a1-130">**Late-Bound Arguments**.</span></span> <span data-ttu-id="827a1-131">如果你想要将后期绑定的对象变量传递给的重载版本，必须声明为适当的参数<xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="827a1-131">If you intend to pass a late bound object variable to an overloaded version, you must declare the appropriate parameter as <xref:System.Object>.</span></span>  
  
## <a name="multiple-versions-of-a-procedure"></a><span data-ttu-id="827a1-132">一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="827a1-132">Multiple Versions of a Procedure</span></span>  
 <span data-ttu-id="827a1-133">假设您要编写`Sub`过程发送事务对客户的余额，和你想要能够按名称或帐户号码，请参阅客户。</span><span class="sxs-lookup"><span data-stu-id="827a1-133">Suppose you are writing a `Sub` procedure to post a transaction against a customer's balance, and you want to be able to refer to the customer either by name or by account number.</span></span> <span data-ttu-id="827a1-134">若要解决此问题，可以定义两个不同`Sub`过程，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="827a1-134">To accommodate this, you can define two different `Sub` procedures, as in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a><span data-ttu-id="827a1-135">重载的版本</span><span class="sxs-lookup"><span data-stu-id="827a1-135">Overloaded Versions</span></span>  
 <span data-ttu-id="827a1-136">一种替代方法是重载的单个过程名称。</span><span class="sxs-lookup"><span data-stu-id="827a1-136">An alternative is to overload a single procedure name.</span></span> <span data-ttu-id="827a1-137">可以使用[重载](../../../../visual-basic/language-reference/modifiers/overloads.md)关键字来定义每个参数列表中，该过程的版本，如下所示：</span><span class="sxs-lookup"><span data-stu-id="827a1-137">You can use the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword to define a version of the procedure for each parameter list, as follows:</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a><span data-ttu-id="827a1-138">其他重载</span><span class="sxs-lookup"><span data-stu-id="827a1-138">Additional Overloads</span></span>  
 <span data-ttu-id="827a1-139">如果还想要接受在事务量`Decimal`或`Single`，可进一步重载`post`允许用于此变体。</span><span class="sxs-lookup"><span data-stu-id="827a1-139">If you also wanted to accept a transaction amount in either `Decimal` or `Single`, you could further overload `post` to allow for this variation.</span></span> <span data-ttu-id="827a1-140">如果执行此操作会为每个重载中前面的示例中，有四个`Sub`过程，所有具有相同名称但具有四个不同的签名。</span><span class="sxs-lookup"><span data-stu-id="827a1-140">If you did this to each of the overloads in the preceding example, you would have four `Sub` procedures, all with the same name but with four different signatures.</span></span>  
  
## <a name="advantages-of-overloading"></a><span data-ttu-id="827a1-141">重载的优点</span><span class="sxs-lookup"><span data-stu-id="827a1-141">Advantages of Overloading</span></span>  
 <span data-ttu-id="827a1-142">重载过程的优点是在调用的灵活性。</span><span class="sxs-lookup"><span data-stu-id="827a1-142">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="827a1-143">若要使用`post`过程声明在前面的示例中，调用代码可以获取为客户标识`String`或`Integer`，然后在任一情况下调用相同的过程。</span><span class="sxs-lookup"><span data-stu-id="827a1-143">To use the `post` procedure declared in the preceding example, the calling code can obtain the customer identification as either a `String` or an `Integer`, and then call the same procedure in either case.</span></span> <span data-ttu-id="827a1-144">下面的示例阐释了这一点：</span><span class="sxs-lookup"><span data-stu-id="827a1-144">The following example illustrates this:</span></span>  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="827a1-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="827a1-145">See also</span></span>
- [<span data-ttu-id="827a1-146">过程</span><span class="sxs-lookup"><span data-stu-id="827a1-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="827a1-147">如何：定义一个过程的多个版本</span><span class="sxs-lookup"><span data-stu-id="827a1-147">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="827a1-148">如何：调用重载的过程</span><span class="sxs-lookup"><span data-stu-id="827a1-148">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="827a1-149">如何：重载带有可选参数的过程</span><span class="sxs-lookup"><span data-stu-id="827a1-149">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="827a1-150">如何：重载的参数数量不确定的过程</span><span class="sxs-lookup"><span data-stu-id="827a1-150">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="827a1-151">重载过程注意事项</span><span class="sxs-lookup"><span data-stu-id="827a1-151">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)
- [<span data-ttu-id="827a1-152">重载决策</span><span class="sxs-lookup"><span data-stu-id="827a1-152">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="827a1-153">重载</span><span class="sxs-lookup"><span data-stu-id="827a1-153">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [<span data-ttu-id="827a1-154">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="827a1-154">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
