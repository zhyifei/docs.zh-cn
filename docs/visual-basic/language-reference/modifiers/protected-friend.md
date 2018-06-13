---
title: 受保护的友元 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: b72cbee0394043620e792d1c014bfe55121e175e
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2018
ms.locfileid: "34306536"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="82a87-102">受保护的友元 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82a87-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="82a87-103">`Protected Friend`关键字组合都是成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="82a87-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="82a87-104">它授予同时[友元](friend.md)访问和[受保护](protected.md)上已声明的元素，这样便可从同一程序集，从其自身的类，以及从派生类中的任何位置访问的访问权限。</span><span class="sxs-lookup"><span data-stu-id="82a87-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="82a87-105">你可以指定`Protected Friend`仅能对成员的类; 不能应用`Protected Friend`结构的成员由于结构不能被继承。</span><span class="sxs-lookup"><span data-stu-id="82a87-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="82a87-106">在 Visual Studio 中，选择 F1 帮助上`protected friend`提供为帮助[保护](protected.md)或[友元](friend.md)。</span><span class="sxs-lookup"><span data-stu-id="82a87-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="82a87-107">IDE 选取下光标，而不是复合 word 单个标记。</span><span class="sxs-lookup"><span data-stu-id="82a87-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="82a87-108">规则</span><span class="sxs-lookup"><span data-stu-id="82a87-108">Rules</span></span>

- <span data-ttu-id="82a87-109">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="82a87-109">**Declaration Context.**</span></span> <span data-ttu-id="82a87-110">你可以使用`Protected Friend`只能在类级别。</span><span class="sxs-lookup"><span data-stu-id="82a87-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="82a87-111">这意味着的声明上下文`Protected`元素必须是类，并且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="82a87-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 


## <a name="see-also"></a><span data-ttu-id="82a87-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="82a87-112">See Also</span></span>

[<span data-ttu-id="82a87-113">Public</span><span class="sxs-lookup"><span data-stu-id="82a87-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="82a87-114">Protected</span><span class="sxs-lookup"><span data-stu-id="82a87-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="82a87-115">[友元](friend.md) </span><span class="sxs-lookup"><span data-stu-id="82a87-115">[Friend](friend.md) </span></span>  
[<span data-ttu-id="82a87-116">Private</span><span class="sxs-lookup"><span data-stu-id="82a87-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="82a87-117">[私有受保护](./private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="82a87-117">[Private Protected](./private-protected.md) </span></span>  
[<span data-ttu-id="82a87-118">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="82a87-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="82a87-119">过程</span><span class="sxs-lookup"><span data-stu-id="82a87-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="82a87-120">结构</span><span class="sxs-lookup"><span data-stu-id="82a87-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="82a87-121">对象和类</span><span class="sxs-lookup"><span data-stu-id="82a87-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
