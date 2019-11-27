---
title: 如何：声明结构
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 41d2d03064dea703909218de56feb863526c220b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350000"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="67d21-102">如何：声明结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67d21-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="67d21-103">使用[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)开始结构声明，并使用 `End Structure` 语句结束。</span><span class="sxs-lookup"><span data-stu-id="67d21-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="67d21-104">在这两个语句之间必须至少声明一个*元素*。</span><span class="sxs-lookup"><span data-stu-id="67d21-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="67d21-105">元素可以是任何数据类型，但必须至少有一个是非共享变量或非共享、非自定义事件。</span><span class="sxs-lookup"><span data-stu-id="67d21-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="67d21-106">不能在结构声明中初始化任何结构元素。</span><span class="sxs-lookup"><span data-stu-id="67d21-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="67d21-107">将变量声明为结构类型时，可以通过变量访问元素，为这些元素赋值。</span><span class="sxs-lookup"><span data-stu-id="67d21-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="67d21-108">有关结构和类之间的差异的讨论，请参阅[结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="67d21-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="67d21-109">出于演示目的，请考虑要跟踪员工姓名、电话分机和薪金的情况。</span><span class="sxs-lookup"><span data-stu-id="67d21-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="67d21-110">结构允许在单个变量中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="67d21-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="67d21-111">声明结构</span><span class="sxs-lookup"><span data-stu-id="67d21-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="67d21-112">为结构创建开始语句和结束语句。</span><span class="sxs-lookup"><span data-stu-id="67d21-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="67d21-113">您可以使用[Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)或[Private](../../../../visual-basic/language-reference/modifiers/private.md)关键字指定结构的访问级别，也可以让其默认 `Public`。</span><span class="sxs-lookup"><span data-stu-id="67d21-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="67d21-114">向结构的主体中添加元素。</span><span class="sxs-lookup"><span data-stu-id="67d21-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="67d21-115">结构中必须至少有一个元素。</span><span class="sxs-lookup"><span data-stu-id="67d21-115">A structure must have at least one element.</span></span> <span data-ttu-id="67d21-116">必须声明每个元素并为其指定访问级别。</span><span class="sxs-lookup"><span data-stu-id="67d21-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="67d21-117">如果使用不带任何关键字的[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)，则可访问性默认为 `Public`。</span><span class="sxs-lookup"><span data-stu-id="67d21-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     <span data-ttu-id="67d21-118">前面的示例中的 "`salary`" 字段是 `Private`的，这意味着它在结构外部不可访问，即使是包含类也是如此。</span><span class="sxs-lookup"><span data-stu-id="67d21-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="67d21-119">但 `Public``giveRaise` 过程，因此可以从结构外部调用它。</span><span class="sxs-lookup"><span data-stu-id="67d21-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="67d21-120">同样，您可以从结构的外部引发 `salaryReviewTime` 事件。</span><span class="sxs-lookup"><span data-stu-id="67d21-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="67d21-121">除了变量、`Sub` 过程和事件外，还可以在结构中定义常量、`Function` 过程和属性。</span><span class="sxs-lookup"><span data-stu-id="67d21-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="67d21-122">最多可以将一个属性指定为*默认属性*，前提是它至少采用一个参数。</span><span class="sxs-lookup"><span data-stu-id="67d21-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="67d21-123">您可以使用[共享](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` 过程处理事件。</span><span class="sxs-lookup"><span data-stu-id="67d21-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="67d21-124">有关详细信息，请参阅[如何：在 Visual Basic 中声明和调用默认属性](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)。</span><span class="sxs-lookup"><span data-stu-id="67d21-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d21-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67d21-125">See also</span></span>

- [<span data-ttu-id="67d21-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="67d21-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="67d21-127">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="67d21-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="67d21-128">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="67d21-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="67d21-129">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="67d21-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="67d21-130">结构</span><span class="sxs-lookup"><span data-stu-id="67d21-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="67d21-131">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="67d21-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="67d21-132">结构变量</span><span class="sxs-lookup"><span data-stu-id="67d21-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="67d21-133">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="67d21-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="67d21-134">结构和类</span><span class="sxs-lookup"><span data-stu-id="67d21-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="67d21-135">用户定义的数据类型</span><span class="sxs-lookup"><span data-stu-id="67d21-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
