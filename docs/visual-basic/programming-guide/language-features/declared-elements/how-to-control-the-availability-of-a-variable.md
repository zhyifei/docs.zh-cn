---
title: 如何：控制变量的可用性 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 84aaeecdbd3cc8ab12589c0342b982bf3f1c8529
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582616"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="8ae6b-102">如何：控制变量的可用性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8ae6b-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="8ae6b-103">可以通过指定变量的*访问级别*来控制变量的可用性。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="8ae6b-104">访问级别确定哪些代码有权读取或写入变量。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
- <span data-ttu-id="8ae6b-105">*成员变量*（在模块级别和在任何过程外部定义）默认为公共访问，这意味着可以看到它们的任何代码都可以访问这些变量。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="8ae6b-106">可以通过指定访问修饰符来更改此。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-106">You can change this by specifying an access modifier.</span></span>  
  
- <span data-ttu-id="8ae6b-107">尽管*本地变量*（在过程中定义）通常具有公共访问权限，但只有其过程中的代码可以访问这些变量。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="8ae6b-108">不能更改本地变量的访问级别，但可以更改包含它的过程的访问级别。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="8ae6b-109">有关详细信息，请参阅[Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="8ae6b-110">私有和公共访问</span><span class="sxs-lookup"><span data-stu-id="8ae6b-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="8ae6b-111">仅允许从其模块、类或结构内部访问变量</span><span class="sxs-lookup"><span data-stu-id="8ae6b-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1. <span data-ttu-id="8ae6b-112">将变量的[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)放入模块、类或结构中，但放在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8ae6b-113">在 `Dim` 语句中包含[Private](../../../../visual-basic/language-reference/modifiers/private.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="8ae6b-114">可以从模块、类或结构中的任何位置读取或写入变量，但不能从外部读取或写入。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="8ae6b-115">使变量可从可查看它的任何代码进行访问</span><span class="sxs-lookup"><span data-stu-id="8ae6b-115">To make a variable accessible from any code that can see it</span></span>  
  
1. <span data-ttu-id="8ae6b-116">对于成员变量，请将变量的 `Dim` 语句放入模块、类或结构中，但放在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8ae6b-117">在 `Dim` 语句中包含[Public](../../../../visual-basic/language-reference/modifiers/public.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="8ae6b-118">可以从与程序集互操作的任何代码读取或写入变量。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="8ae6b-119">或</span><span class="sxs-lookup"><span data-stu-id="8ae6b-119">-or-</span></span>  
  
1. <span data-ttu-id="8ae6b-120">对于局部变量，请将变量的 `Dim` 语句放置到过程内。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2. <span data-ttu-id="8ae6b-121">不要在 `Dim` 语句中包含 `Public` 关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="8ae6b-122">可以从过程中的任何位置读取或写入变量，但不能从外部读取或写入。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="8ae6b-123">受保护和友元访问</span><span class="sxs-lookup"><span data-stu-id="8ae6b-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="8ae6b-124">可以将变量的访问级别限制为其类和派生类，或限制为其程序集。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="8ae6b-125">您还可以指定这些限制的联合，这允许从任何派生类中的代码或同一程序集中的任何其他位置进行访问。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="8ae6b-126">通过组合同一声明中的 `Protected` 和 `Friend` 关键字来指定此联合。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="8ae6b-127">使变量只能从其类和任何派生类中访问</span><span class="sxs-lookup"><span data-stu-id="8ae6b-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1. <span data-ttu-id="8ae6b-128">将变量的 `Dim` 语句放置在类中，但在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8ae6b-129">在 `Dim` 语句中包含[Protected](../../../../visual-basic/language-reference/modifiers/protected.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="8ae6b-130">可以从类中的任何位置以及从派生的任何类（而不是从派生链中的任何类）读取或写入变量。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="8ae6b-131">使变量只能从同一程序集内访问</span><span class="sxs-lookup"><span data-stu-id="8ae6b-131">To make a variable accessible only from within the same assembly</span></span>  
  
1. <span data-ttu-id="8ae6b-132">将变量的 `Dim` 语句放入模块、类或结构中，但在任何过程之外。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2. <span data-ttu-id="8ae6b-133">在 `Dim` 语句中包含[Friend](../../../../visual-basic/language-reference/modifiers/friend.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="8ae6b-134">你可以从模块、类或结构中的任何位置读取或写入变量，也可以从同一程序集中的任何代码读取或写入到程序集之外的任何代码。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ae6b-135">示例</span><span class="sxs-lookup"><span data-stu-id="8ae6b-135">Example</span></span>  
 <span data-ttu-id="8ae6b-136">下面的示例演示具有 `Public`、`Protected`、`Friend`、`Protected Friend` 和 `Private` 访问级别的变量的声明。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="8ae6b-137">请注意，如果 `Dim` 语句指定了访问级别，则不需要包括 `Dim` 关键字。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="8ae6b-138">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="8ae6b-138">.NET Framework Security</span></span>  
 <span data-ttu-id="8ae6b-139">变量访问级别的限制性越多，恶意代码使用它的可能性就越小。</span><span class="sxs-lookup"><span data-stu-id="8ae6b-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ae6b-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ae6b-140">See also</span></span>

- [<span data-ttu-id="8ae6b-141">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="8ae6b-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="8ae6b-142">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="8ae6b-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="8ae6b-143">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="8ae6b-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="8ae6b-144">Protected</span><span class="sxs-lookup"><span data-stu-id="8ae6b-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="8ae6b-145">Friend</span><span class="sxs-lookup"><span data-stu-id="8ae6b-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="8ae6b-146">Private</span><span class="sxs-lookup"><span data-stu-id="8ae6b-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
