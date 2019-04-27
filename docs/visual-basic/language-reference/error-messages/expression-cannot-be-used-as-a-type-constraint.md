---
title: “<expression>”不能用作类型约束
ms.date: 07/20/2015
f1_keywords:
- bc32061
- vbc32061
helpviewer_keywords:
- BC32061
ms.assetid: b17821b7-fa14-4397-a211-6e2a14079f09
ms.openlocfilehash: 8dbf510d7c6ee80e2dcd2f9d2552bc870413cbab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801473"
---
# <a name="expression-cannot-be-used-as-a-type-constraint"></a><span data-ttu-id="a1d1d-102">\<表达式 > 不能用作类型约束</span><span class="sxs-lookup"><span data-stu-id="a1d1d-102">'\<expression>' cannot be used as a type constraint</span></span>
<span data-ttu-id="a1d1d-103">约束列表包含的表达式不表示对类型形参的有效约束。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-103">A constraint list includes an expression that does not represent a valid constraint on a type parameter.</span></span>  
  
 <span data-ttu-id="a1d1d-104">约束列表对传递给类型形参的类型实参有一定要求。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-104">A constraint list imposes requirements on the type argument passed to the type parameter.</span></span> <span data-ttu-id="a1d1d-105">你可以采用任意组合指定以下要求：</span><span class="sxs-lookup"><span data-stu-id="a1d1d-105">You can specify the following requirements in any combination:</span></span>  
  
-   <span data-ttu-id="a1d1d-106">该类型实参必须实现一个或多个接口</span><span class="sxs-lookup"><span data-stu-id="a1d1d-106">The type argument must implement one or more interfaces</span></span>  
  
-   <span data-ttu-id="a1d1d-107">该类型实参最多从一个类继承</span><span class="sxs-lookup"><span data-stu-id="a1d1d-107">The type argument must inherit from at most one class</span></span>  
  
-   <span data-ttu-id="a1d1d-108">类型实参必须公开一个创建代码可以访问的无形参构造函数（包括 `New` 约束）</span><span class="sxs-lookup"><span data-stu-id="a1d1d-108">The type argument must expose a parameterless constructor that the creating code can access (include the `New` constraint)</span></span>  
  
 <span data-ttu-id="a1d1d-109">如果不在约束列表中包括任何特定类或接口，则可以通过指定以下内容之一来施加更常规的要求：</span><span class="sxs-lookup"><span data-stu-id="a1d1d-109">If you do not include any specific class or interface in the constraint list, you can impose a more general requirement by specifying one of the following:</span></span>  
  
-   <span data-ttu-id="a1d1d-110">类型参数必须是值类型（包括 `Structure` 约束）</span><span class="sxs-lookup"><span data-stu-id="a1d1d-110">The type argument must be a value type (include the `Structure` constraint)</span></span>  
  
-   <span data-ttu-id="a1d1d-111">类型参数必须是引用类型（包括 `Class` 约束）</span><span class="sxs-lookup"><span data-stu-id="a1d1d-111">The type argument must be a reference type (include the `Class` constraint)</span></span>  
  
 <span data-ttu-id="a1d1d-112">不能为同一类型参数同时指定 `Structure` 和 `Class` ，并且它们两个都只能指定一次。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-112">You cannot specify both `Structure` and `Class` for the same type parameter, and you cannot specify either one more than once.</span></span>  
  
 <span data-ttu-id="a1d1d-113">**错误 ID:** BC32061</span><span class="sxs-lookup"><span data-stu-id="a1d1d-113">**Error ID:** BC32061</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a1d1d-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a1d1d-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a1d1d-115">验证表达式及其元素是否拼写正确。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-115">Verify that the expression and its elements are spelled correctly.</span></span>  
  
-   <span data-ttu-id="a1d1d-116">如果表达式不符合前面列出的要求，请从约束列表中将其删除。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-116">If the expression does not qualify for the preceding list of requirements, remove it from the constraint list.</span></span>  
  
-   <span data-ttu-id="a1d1d-117">如果表达式引用接口或类，请验证编译器是否有权访问该接口或类。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-117">If the expression refers to an interface or class, verify that the compiler has access to that interface or class.</span></span> <span data-ttu-id="a1d1d-118">可能需要限定其名称，并可能需要添加一个项目引用。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-118">You might need to qualify its name, and you might need to add a reference to your project.</span></span> <span data-ttu-id="a1d1d-119">详细信息，请参阅"项目引用"中[References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1d1d-119">For more information, see "References to Projects" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d1d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1d1d-120">See also</span></span>

- [<span data-ttu-id="a1d1d-121">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="a1d1d-121">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a1d1d-122">值类型和引用类型</span><span class="sxs-lookup"><span data-stu-id="a1d1d-122">Value Types and Reference Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="a1d1d-123">对已声明元素的引用</span><span class="sxs-lookup"><span data-stu-id="a1d1d-123">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
