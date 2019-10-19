---
title: Implements 语句（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 865e99aa0e27591d10fde1465047a2e6bf183bbf
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581790"
---
# <a name="implements-statement"></a><span data-ttu-id="b66e4-102">Implements 语句</span><span class="sxs-lookup"><span data-stu-id="b66e4-102">Implements Statement</span></span>
<span data-ttu-id="b66e4-103">指定一个或多个接口或接口成员，它们必须在它所出现的类或结构定义中实现。</span><span class="sxs-lookup"><span data-stu-id="b66e4-103">Specifies one or more interfaces, or interface members, that must be implemented in the class or structure definition in which it appears.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b66e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="b66e4-104">Syntax</span></span>  
  
```vb  
Implements interfacename [, ...]  
' -or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a><span data-ttu-id="b66e4-105">部件</span><span class="sxs-lookup"><span data-stu-id="b66e4-105">Parts</span></span>  
 `interfacename`  
 <span data-ttu-id="b66e4-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="b66e4-106">Required.</span></span> <span data-ttu-id="b66e4-107">一个接口，其属性、过程和事件由类或结构中的相应成员实现。</span><span class="sxs-lookup"><span data-stu-id="b66e4-107">An interface whose properties, procedures, and events are to be implemented by corresponding members in the class or structure.</span></span>  
  
 `interfacemember`  
 <span data-ttu-id="b66e4-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="b66e4-108">Required.</span></span> <span data-ttu-id="b66e4-109">正在实现的接口的成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-109">The member of an interface that is being implemented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b66e4-110">备注</span><span class="sxs-lookup"><span data-stu-id="b66e4-110">Remarks</span></span>  
 <span data-ttu-id="b66e4-111">接口是表示接口封装的成员（属性、过程和事件）的原型的集合。</span><span class="sxs-lookup"><span data-stu-id="b66e4-111">An interface is a collection of prototypes representing the members (properties, procedures, and events) the interface encapsulates.</span></span> <span data-ttu-id="b66e4-112">接口只包含成员的声明;类和结构实现这些成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-112">Interfaces contain only the declarations for members; classes and structures implement these members.</span></span> <span data-ttu-id="b66e4-113">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b66e4-113">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b66e4-114">@No__t_0 语句必须紧跟在 `Class` 或 `Structure` 语句之后。</span><span class="sxs-lookup"><span data-stu-id="b66e4-114">The `Implements` statement must immediately follow the `Class` or `Structure` statement.</span></span>  
  
 <span data-ttu-id="b66e4-115">实现接口时，必须实现在接口中声明的所有成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-115">When you implement an interface, you must implement all the members declared in the interface.</span></span> <span data-ttu-id="b66e4-116">省略任何成员均视为语法错误。</span><span class="sxs-lookup"><span data-stu-id="b66e4-116">Omitting any member is considered to be a syntax error.</span></span> <span data-ttu-id="b66e4-117">若要实现单个成员，请在声明类或结构中的成员时指定[Implements](../../../visual-basic/language-reference/statements/implements-clause.md)关键字（与 `Implements` 语句分开）。</span><span class="sxs-lookup"><span data-stu-id="b66e4-117">To implement an individual member, you specify the [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) keyword (which is separate from the `Implements` statement) when you declare the member in the class or structure.</span></span> <span data-ttu-id="b66e4-118">有关详细信息，请参阅[接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b66e4-118">For more information, see [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="b66e4-119">类可以使用属性和过程的[私有](../../../visual-basic/language-reference/modifiers/private.md)实现，但只能通过将实现类的实例强制转换为声明为接口类型的变量来访问这些成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-119">Classes can use [Private](../../../visual-basic/language-reference/modifiers/private.md) implementations of properties and procedures, but these members are accessible only by casting an instance of the implementing class into a variable declared to be of the type of the interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b66e4-120">示例</span><span class="sxs-lookup"><span data-stu-id="b66e4-120">Example</span></span>  
 <span data-ttu-id="b66e4-121">下面的示例演示如何使用 `Implements` 语句来实现接口的成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-121">The following example shows how to use the `Implements` statement to implement members of an interface.</span></span> <span data-ttu-id="b66e4-122">它使用事件、属性和过程来定义名为 `ICustomerInfo` 的接口。</span><span class="sxs-lookup"><span data-stu-id="b66e4-122">It defines an interface named `ICustomerInfo` with an event, a property, and a procedure.</span></span> <span data-ttu-id="b66e4-123">类 `customerInfo` 实现在接口中定义的所有成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-123">The class `customerInfo` implements all the members defined in the interface.</span></span>  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 <span data-ttu-id="b66e4-124">请注意，类 `customerInfo` 对单独的源代码行使用 `Implements` 语句，以指示类实现了 `ICustomerInfo` 接口的所有成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-124">Note that the class `customerInfo` uses the `Implements` statement on a separate source code line to indicate that the class implements all the members of the `ICustomerInfo` interface.</span></span> <span data-ttu-id="b66e4-125">然后，类中的每个成员都使用 `Implements` 关键字作为其成员声明的一部分，以指示它实现了该接口成员。</span><span class="sxs-lookup"><span data-stu-id="b66e4-125">Then each member in the class uses the `Implements` keyword as part of its member declaration to indicate that it implements that interface member.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b66e4-126">示例</span><span class="sxs-lookup"><span data-stu-id="b66e4-126">Example</span></span>  
 <span data-ttu-id="b66e4-127">下面的两个过程演示如何使用在前面的示例中实现的接口。</span><span class="sxs-lookup"><span data-stu-id="b66e4-127">The following two procedures show how you could use the interface implemented in the preceding example.</span></span> <span data-ttu-id="b66e4-128">若要测试实现，请将这些过程添加到项目中，然后调用 `testImplements` 过程。</span><span class="sxs-lookup"><span data-stu-id="b66e4-128">To test the implementation, add these procedures to your project and call the `testImplements` procedure.</span></span>  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="b66e4-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b66e4-129">See also</span></span>

- [<span data-ttu-id="b66e4-130">Sub New</span><span class="sxs-lookup"><span data-stu-id="b66e4-130">Implements</span></span>](../../../visual-basic/language-reference/statements/implements-clause.md)
- [<span data-ttu-id="b66e4-131">Interface 语句</span><span class="sxs-lookup"><span data-stu-id="b66e4-131">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="b66e4-132">接口</span><span class="sxs-lookup"><span data-stu-id="b66e4-132">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
