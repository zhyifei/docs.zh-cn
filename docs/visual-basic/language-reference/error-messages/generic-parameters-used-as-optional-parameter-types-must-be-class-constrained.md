---
title: 用作可选参数类型的泛型参数必须受类约束
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="f27e9-102">用作可选参数类型的泛型参数必须受类约束</span><span class="sxs-lookup"><span data-stu-id="f27e9-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="f27e9-103">使用不约束为引用类型的类型参数的可选参数声明的过程。</span><span class="sxs-lookup"><span data-stu-id="f27e9-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="f27e9-104">你必须始终提供每个可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="f27e9-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="f27e9-105">如果参数是引用类型，则可选值必须为`Nothing`，是一个有效的值，对于任何引用类型。</span><span class="sxs-lookup"><span data-stu-id="f27e9-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="f27e9-106">但是，如果参数的值类型，则该类型必须由 Visual Basic 预定义的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="f27e9-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="f27e9-107">这是因为复合值类型，如用户定义的结构，不具有任何有效的默认值。</span><span class="sxs-lookup"><span data-stu-id="f27e9-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="f27e9-108">当你使用的类型参数为可选参数时，必须保证它属于引用类型以避免任何有效的默认值的值类型的可能性。</span><span class="sxs-lookup"><span data-stu-id="f27e9-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="f27e9-109">这意味着必须与约束类型参数`Class`关键字或特定类的名称。</span><span class="sxs-lookup"><span data-stu-id="f27e9-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="f27e9-110">**错误 ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="f27e9-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f27e9-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f27e9-111">To correct this error</span></span>  
  
-   <span data-ttu-id="f27e9-112">将仅接受一个引用类型，类型参数约束，或者不使用它为可选参数。</span><span class="sxs-lookup"><span data-stu-id="f27e9-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27e9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f27e9-113">See Also</span></span>  
 [<span data-ttu-id="f27e9-114">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="f27e9-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="f27e9-115">类型列表</span><span class="sxs-lookup"><span data-stu-id="f27e9-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="f27e9-116">Class 语句</span><span class="sxs-lookup"><span data-stu-id="f27e9-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="f27e9-117">可选参数</span><span class="sxs-lookup"><span data-stu-id="f27e9-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="f27e9-118">结构</span><span class="sxs-lookup"><span data-stu-id="f27e9-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="f27e9-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="f27e9-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
