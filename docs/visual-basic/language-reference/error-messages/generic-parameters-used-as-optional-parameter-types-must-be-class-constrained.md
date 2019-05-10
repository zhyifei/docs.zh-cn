---
title: 用作可选参数类型的泛型参数必须受类约束
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 11cf4f8d9457ebff385a601786dc97334f274324
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662062"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="3f2fa-102">用作可选参数类型的泛型参数必须受类约束</span><span class="sxs-lookup"><span data-stu-id="3f2fa-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="3f2fa-103">使用可选参数使用不受约束为引用类型的类型参数声明的过程。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="3f2fa-104">您必须始终提供每个可选参数的默认值。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="3f2fa-105">如果参数为引用类型，可选的值必须为`Nothing`，这是对于任何引用类型的有效值。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="3f2fa-106">但是，如果该参数的值类型，该类型必须是预定义的 Visual basic 的基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="3f2fa-107">这是因为复合值类型，例如，用户定义的结构，有没有有效默认值。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="3f2fa-108">当您使用的类型参数为可选参数时，必须保证它属于引用类型以避免包含任何有效的默认值的值类型的可能性。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="3f2fa-109">这意味着必须使用约束类型参数`Class`关键字或具有特定类的名称。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="3f2fa-110">**错误 ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="3f2fa-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3f2fa-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="3f2fa-111">To correct this error</span></span>  
  
- <span data-ttu-id="3f2fa-112">约束类型参数以接受仅为引用类型，或不使用它为可选参数。</span><span class="sxs-lookup"><span data-stu-id="3f2fa-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f2fa-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f2fa-113">See also</span></span>

- [<span data-ttu-id="3f2fa-114">Visual Basic 中的泛型类型</span><span class="sxs-lookup"><span data-stu-id="3f2fa-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="3f2fa-115">类型列表</span><span class="sxs-lookup"><span data-stu-id="3f2fa-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="3f2fa-116">Class 语句</span><span class="sxs-lookup"><span data-stu-id="3f2fa-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="3f2fa-117">可选参数</span><span class="sxs-lookup"><span data-stu-id="3f2fa-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="3f2fa-118">结构</span><span class="sxs-lookup"><span data-stu-id="3f2fa-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="3f2fa-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="3f2fa-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
