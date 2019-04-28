---
title: 如何：声明结构 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906706"
---
# <a name="how-to-declare-a-structure-visual-basic"></a><span data-ttu-id="c3177-102">如何：声明结构 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3177-102">How to: Declare a Structure (Visual Basic)</span></span>
<span data-ttu-id="c3177-103">在开始使用在结构声明[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)，并结束与`End Structure`语句。</span><span class="sxs-lookup"><span data-stu-id="c3177-103">You begin a structure declaration with the [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md), and you end it with the `End Structure` statement.</span></span> <span data-ttu-id="c3177-104">这两个语句之间必须声明至少一个*元素*。</span><span class="sxs-lookup"><span data-stu-id="c3177-104">Between these two statements you must declare at least one *element*.</span></span> <span data-ttu-id="c3177-105">元素可以是任何数据类型，但至少一个必须为非共享的变量或非共享、 非自定义事件。</span><span class="sxs-lookup"><span data-stu-id="c3177-105">The elements can be of any data type, but at least one must be either a nonshared variable or a nonshared, noncustom event.</span></span>  
  
 <span data-ttu-id="c3177-106">无法初始化任何在结构声明中的结构元素。</span><span class="sxs-lookup"><span data-stu-id="c3177-106">You cannot initialize any of the structure elements in the structure declaration.</span></span> <span data-ttu-id="c3177-107">声明变量为结构类型时，将值的元素分配通过它们访问通过变量。</span><span class="sxs-lookup"><span data-stu-id="c3177-107">When you declare a variable to be of a structure type, you assign values to the elements by accessing them through the variable.</span></span>  
  
 <span data-ttu-id="c3177-108">结构和类之间的差异的讨论，请参阅[结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="c3177-108">For a discussion of the differences between structures and classes, see [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).</span></span>  
  
 <span data-ttu-id="c3177-109">出于演示目的，假设你想要跟踪的员工的名称、 电话分机和薪金。</span><span class="sxs-lookup"><span data-stu-id="c3177-109">For demonstration purposes, consider a situation where you want to keep track of an employee's name, telephone extension, and salary.</span></span> <span data-ttu-id="c3177-110">一种结构，可在一个变量执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c3177-110">A structure allows you to do this in a single variable.</span></span>  
  
### <a name="to-declare-a-structure"></a><span data-ttu-id="c3177-111">若要声明结构</span><span class="sxs-lookup"><span data-stu-id="c3177-111">To declare a structure</span></span>  
  
1. <span data-ttu-id="c3177-112">创建的开始和结束语句的结构。</span><span class="sxs-lookup"><span data-stu-id="c3177-112">Create the beginning and ending statements for the structure.</span></span>  
  
     <span data-ttu-id="c3177-113">可以指定的结构使用的访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)，或者[专用](../../../../visual-basic/language-reference/modifiers/private.md)关键字，或者您可以让它默认为`Public`。</span><span class="sxs-lookup"><span data-stu-id="c3177-113">You can specify the access level of a structure using the [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), or [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword, or you can let it default to `Public`.</span></span>  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. <span data-ttu-id="c3177-114">将元素添加到结构的正文。</span><span class="sxs-lookup"><span data-stu-id="c3177-114">Add elements to the body of the structure.</span></span>  
  
     <span data-ttu-id="c3177-115">一种结构必须具有至少一个元素。</span><span class="sxs-lookup"><span data-stu-id="c3177-115">A structure must have at least one element.</span></span> <span data-ttu-id="c3177-116">必须声明每个元素，并为其指定访问级别。</span><span class="sxs-lookup"><span data-stu-id="c3177-116">You must declare every element and specify an access level for it.</span></span> <span data-ttu-id="c3177-117">如果您使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)而无需任何关键字，可访问性默认为`Public`。</span><span class="sxs-lookup"><span data-stu-id="c3177-117">If you use the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) without any keywords, the accessibility defaults to `Public`.</span></span>  
  
    ```  
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
  
     <span data-ttu-id="c3177-118">`salary`前面的示例中的字段是`Private`，这意味着它是结构之外，甚至自包含类不能访问。</span><span class="sxs-lookup"><span data-stu-id="c3177-118">The `salary` field in the preceding example is `Private`, which means it is inaccessible outside the structure, even from the containing class.</span></span> <span data-ttu-id="c3177-119">但是，`giveRaise`过程是`Public`，因此它可以从调用，结构之外。</span><span class="sxs-lookup"><span data-stu-id="c3177-119">However, the `giveRaise` procedure is `Public`, so it can be called from outside the structure.</span></span> <span data-ttu-id="c3177-120">同样，你可以将提升`salaryReviewTime`从结构之外的事件。</span><span class="sxs-lookup"><span data-stu-id="c3177-120">Similarly, you can raise the `salaryReviewTime` event from outside the structure.</span></span>  
  
     <span data-ttu-id="c3177-121">除了变量，还`Sub`过程和事件，您还可以定义常量、`Function`过程和结构中的属性。</span><span class="sxs-lookup"><span data-stu-id="c3177-121">In addition to variables, `Sub` procedures, and events, you can also define constants, `Function` procedures, and properties in a structure.</span></span> <span data-ttu-id="c3177-122">您可以指定最多一个属性作为*默认属性*，提供它采用至少一个自变量。</span><span class="sxs-lookup"><span data-stu-id="c3177-122">You can designate at most one property as the *default property*, provided it takes at least one argument.</span></span> <span data-ttu-id="c3177-123">您可以处理的事件[共享](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub`过程。</span><span class="sxs-lookup"><span data-stu-id="c3177-123">You can handle an event with a [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` procedure.</span></span> <span data-ttu-id="c3177-124">有关详细信息，请参阅[如何：声明和调用默认属性在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)。</span><span class="sxs-lookup"><span data-stu-id="c3177-124">For more information, see [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3177-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3177-125">See also</span></span>

- [<span data-ttu-id="c3177-126">数据类型</span><span class="sxs-lookup"><span data-stu-id="c3177-126">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="c3177-127">基本数据类型</span><span class="sxs-lookup"><span data-stu-id="c3177-127">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="c3177-128">复合数据类型</span><span class="sxs-lookup"><span data-stu-id="c3177-128">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="c3177-129">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="c3177-129">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="c3177-130">结构</span><span class="sxs-lookup"><span data-stu-id="c3177-130">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="c3177-131">数据类型疑难解答</span><span class="sxs-lookup"><span data-stu-id="c3177-131">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="c3177-132">结构变量</span><span class="sxs-lookup"><span data-stu-id="c3177-132">Structure Variables</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [<span data-ttu-id="c3177-133">结构和其他编程元素</span><span class="sxs-lookup"><span data-stu-id="c3177-133">Structures and Other Programming Elements</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [<span data-ttu-id="c3177-134">结构和类</span><span class="sxs-lookup"><span data-stu-id="c3177-134">Structures and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [<span data-ttu-id="c3177-135">用户定义的数据类型</span><span class="sxs-lookup"><span data-stu-id="c3177-135">User-Defined Data Type</span></span>](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
