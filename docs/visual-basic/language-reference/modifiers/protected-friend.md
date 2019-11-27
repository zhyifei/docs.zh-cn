---
title: Protected Friend
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: f92021f5f0dab9762470c270bdd5182187d587e5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351322"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="a0587-102">受保护的朋友（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="a0587-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="a0587-103">`Protected Friend` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="a0587-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="a0587-104">它在已声明的元素上授予[朋友](friend.md)访问和[受保护](protected.md)的访问，因此可以从同一程序集中的任何位置、从其自己的类和派生类中访问它们。</span><span class="sxs-lookup"><span data-stu-id="a0587-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="a0587-105">只能在类的成员上指定 `Protected Friend`;无法将 `Protected Friend` 应用到结构的成员，因为结构不能继承。</span><span class="sxs-lookup"><span data-stu-id="a0587-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="a0587-106">在 Visual Studio 中，选择 `protected friend` 上的 F1 帮助为[受保护](protected.md)的或[朋友](friend.md)提供帮助。</span><span class="sxs-lookup"><span data-stu-id="a0587-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="a0587-107">IDE 将选取光标下的单个标记，而不是组合词。</span><span class="sxs-lookup"><span data-stu-id="a0587-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="a0587-108">规则</span><span class="sxs-lookup"><span data-stu-id="a0587-108">Rules</span></span>

<span data-ttu-id="a0587-109">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="a0587-109">**Declaration Context.**</span></span> <span data-ttu-id="a0587-110">只能在类级别使用 `Protected Friend`。</span><span class="sxs-lookup"><span data-stu-id="a0587-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="a0587-111">这意味着 `Protected` 元素的声明上下文必须是类，且不能是源文件、命名空间、接口、模块、结构或过程。</span><span class="sxs-lookup"><span data-stu-id="a0587-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0587-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0587-112">See also</span></span>

- [<span data-ttu-id="a0587-113">Public</span><span class="sxs-lookup"><span data-stu-id="a0587-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="a0587-114">Protected</span><span class="sxs-lookup"><span data-stu-id="a0587-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="a0587-115">Friend</span><span class="sxs-lookup"><span data-stu-id="a0587-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="a0587-116">Private</span><span class="sxs-lookup"><span data-stu-id="a0587-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="a0587-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="a0587-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="a0587-118">Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="a0587-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="a0587-119">过程</span><span class="sxs-lookup"><span data-stu-id="a0587-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="a0587-120">结构</span><span class="sxs-lookup"><span data-stu-id="a0587-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="a0587-121">对象和类</span><span class="sxs-lookup"><span data-stu-id="a0587-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
