---
title: 如何：控制变量 (Visual Basic 中) 的可用性
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
ms.openlocfilehash: fb7c04ac6c24648dfb2a8cfa5e01bf97c6b0b3be
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841688"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a><span data-ttu-id="79db1-102">如何：控制变量 (Visual Basic 中) 的可用性</span><span class="sxs-lookup"><span data-stu-id="79db1-102">How to: Control the Availability of a Variable (Visual Basic)</span></span>
<span data-ttu-id="79db1-103">通过指定控制变量的可用性及其*访问级别*。</span><span class="sxs-lookup"><span data-stu-id="79db1-103">You control the availability of a variable by specifying its *access level*.</span></span> <span data-ttu-id="79db1-104">访问级别确定哪些代码有权读取或写入到该变量。</span><span class="sxs-lookup"><span data-stu-id="79db1-104">The access level determines what code has permission to read or write to the variable.</span></span>  
  
-   <span data-ttu-id="79db1-105">*成员变量*（定义在模块级别和任何过程之外） 默认为公共访问，这意味着用户可以看见任何代码可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="79db1-105">*Member variables* (defined at module level and outside any procedure) default to public access, which means any code that can see them can access them.</span></span> <span data-ttu-id="79db1-106">可以通过指定访问修饰符对此进行更改。</span><span class="sxs-lookup"><span data-stu-id="79db1-106">You can change this by specifying an access modifier.</span></span>  
  
-   <span data-ttu-id="79db1-107">*本地变量*（定义在过程内） 名义上具有公共访问，虽然只有其过程中的代码可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="79db1-107">*Local variables* (defined inside a procedure) nominally have public access, although only code within their procedure can access them.</span></span> <span data-ttu-id="79db1-108">不能更改访问级别的本地变量，但可以更改包含它的过程的访问级别。</span><span class="sxs-lookup"><span data-stu-id="79db1-108">You cannot change the access level of a local variable, but you can change the access level of the procedure that contains it.</span></span>  
  
 <span data-ttu-id="79db1-109">有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="79db1-109">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="private-and-public-access"></a><span data-ttu-id="79db1-110">专用和公共访问</span><span class="sxs-lookup"><span data-stu-id="79db1-110">Private and Public Access</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a><span data-ttu-id="79db1-111">若要使变量只能在其模块、 类或结构内访问</span><span class="sxs-lookup"><span data-stu-id="79db1-111">To make a variable accessible only from within its module, class, or structure</span></span>  
  
1.  <span data-ttu-id="79db1-112">位置[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)内部模块、 类或结构，但在任何过程外部的变量。</span><span class="sxs-lookup"><span data-stu-id="79db1-112">Place the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) for the variable inside the module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="79db1-113">包括[私有](../../../../visual-basic/language-reference/modifiers/private.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-113">Include the [Private](../../../../visual-basic/language-reference/modifiers/private.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79db1-114">可以读取或写入到中的变量中的模块、 类或结构的任意位置，但不能从其外部。</span><span class="sxs-lookup"><span data-stu-id="79db1-114">You can read or write to the variable from anywhere within the module, class, or structure, but not from outside it.</span></span>  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a><span data-ttu-id="79db1-115">若要使变量可从任何可以看到它的代码访问</span><span class="sxs-lookup"><span data-stu-id="79db1-115">To make a variable accessible from any code that can see it</span></span>  
  
1.  <span data-ttu-id="79db1-116">成员变量，将放置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-116">For a member variable, place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="79db1-117">包括[公共](../../../../visual-basic/language-reference/modifiers/public.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-117">Include the [Public](../../../../visual-basic/language-reference/modifiers/public.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79db1-118">可读取或从任何互操作的代码与您的程序集写入变量。</span><span class="sxs-lookup"><span data-stu-id="79db1-118">You can read or write to the variable from any code that interoperates with your assembly.</span></span>  
  
 <span data-ttu-id="79db1-119">或</span><span class="sxs-lookup"><span data-stu-id="79db1-119">-or-</span></span>  
  
1.  <span data-ttu-id="79db1-120">本地变量，将放置`Dim`过程内的变量的语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-120">For a local variable, place the `Dim` statement for the variable inside a procedure.</span></span>  
  
2.  <span data-ttu-id="79db1-121">不包括`Public`中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-121">Do not include the `Public` keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79db1-122">你可以读取或写入过程中的任意位置，但不能从变量到其外部。</span><span class="sxs-lookup"><span data-stu-id="79db1-122">You can read or write to the variable from anywhere within the procedure, but not from outside it.</span></span>  
  
## <a name="protected-and-friend-access"></a><span data-ttu-id="79db1-123">受保护和友元访问权限</span><span class="sxs-lookup"><span data-stu-id="79db1-123">Protected and Friend Access</span></span>  
 <span data-ttu-id="79db1-124">您可以限制到其类和任何派生的类，或它的程序集的变量的访问级别。</span><span class="sxs-lookup"><span data-stu-id="79db1-124">You can limit the access level of a variable to its class and any derived classes, or to its assembly.</span></span> <span data-ttu-id="79db1-125">此外可以指定这些限制，可从代码访问权限，任何派生类中或在同一程序集中的任何其他位置中的并集。</span><span class="sxs-lookup"><span data-stu-id="79db1-125">You can also specify the union of these limitations, which allows access from code in any derived class or in any other place in the same assembly.</span></span> <span data-ttu-id="79db1-126">通过组合指定了此 union`Protected`和`Friend`同一声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="79db1-126">You specify this union by combining the `Protected` and `Friend` keywords in the same declaration.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a><span data-ttu-id="79db1-127">若要使变量只能从其类和任何派生的类中访问</span><span class="sxs-lookup"><span data-stu-id="79db1-127">To make a variable accessible only from within its class and any derived classes</span></span>  
  
1.  <span data-ttu-id="79db1-128">位置`Dim`类的内部，但在任何过程外部变量的语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-128">Place the `Dim` statement for the variable inside a class, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="79db1-129">包括[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-129">Include the [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79db1-130">可读取或写入任意位置在类中，以及从变量的任何类派生，但不能从任何类进行派生链中的外部。</span><span class="sxs-lookup"><span data-stu-id="79db1-130">You can read or write to the variable from anywhere within the class, as well as from within any class derived from it, but not from outside any class in the derivation chain.</span></span>  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a><span data-ttu-id="79db1-131">若要使变量只能在同一程序集内访问</span><span class="sxs-lookup"><span data-stu-id="79db1-131">To make a variable accessible only from within the same assembly</span></span>  
  
1.  <span data-ttu-id="79db1-132">位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-132">Place the `Dim` statement for the variable inside a module, class, or structure, but outside any procedure.</span></span>  
  
2.  <span data-ttu-id="79db1-133">包括[友元](../../../../visual-basic/language-reference/modifiers/friend.md)中的关键字`Dim`语句。</span><span class="sxs-lookup"><span data-stu-id="79db1-133">Include the [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) keyword in the `Dim` statement.</span></span>  
  
     <span data-ttu-id="79db1-134">可读取或写入模块、 类或结构中的任意位置以及从同一程序集中，但不能从任何代码从变量到程序集之外。</span><span class="sxs-lookup"><span data-stu-id="79db1-134">You can read or write to the variable from anywhere within the module, class, or structure, as well as from any code in the same assembly, but not from outside the assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79db1-135">示例</span><span class="sxs-lookup"><span data-stu-id="79db1-135">Example</span></span>  
 <span data-ttu-id="79db1-136">下面的示例演示使用的变量的声明`Public`， `Protected`， `Friend`， `Protected Friend`，和`Private`访问级别。</span><span class="sxs-lookup"><span data-stu-id="79db1-136">The following example shows declarations of variables with `Public`, `Protected`, `Friend`, `Protected Friend`, and `Private` access levels.</span></span> <span data-ttu-id="79db1-137">请注意，当`Dim`语句指定访问级别时，不需要包括`Dim`关键字。</span><span class="sxs-lookup"><span data-stu-id="79db1-137">Note that when the `Dim` statement specifies an access level, you do not need to include the `Dim` keyword.</span></span>  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a><span data-ttu-id="79db1-138">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="79db1-138">.NET Framework Security</span></span>  
 <span data-ttu-id="79db1-139">限制性更强的变量的访问级别，使用它的变量越小恶意代码可以进行不正确的机会。</span><span class="sxs-lookup"><span data-stu-id="79db1-139">The more restrictive the access level of a variable, the smaller the chances that malicious code can make improper use of it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79db1-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="79db1-140">See also</span></span>

- [<span data-ttu-id="79db1-141">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="79db1-141">Access levels in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="79db1-142">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="79db1-142">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="79db1-143">Public</span><span class="sxs-lookup"><span data-stu-id="79db1-143">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="79db1-144">Protected</span><span class="sxs-lookup"><span data-stu-id="79db1-144">Protected</span></span>](../../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="79db1-145">Friend</span><span class="sxs-lookup"><span data-stu-id="79db1-145">Friend</span></span>](../../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="79db1-146">Private</span><span class="sxs-lookup"><span data-stu-id="79db1-146">Private</span></span>](../../../../visual-basic/language-reference/modifiers/private.md)
