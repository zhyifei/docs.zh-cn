---
title: 受保护的友元 (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151770"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="9432e-102">受保护的友元 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9432e-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="9432e-103">`Protected Friend` 关键字组合是一种成员访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="9432e-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="9432e-104">它授予这两[友元](friend.md)访问权限和[受保护](protected.md)上声明的元素，因此它们可从同一程序集，从其自身的类，以及从派生类中的任意位置访问的访问。</span><span class="sxs-lookup"><span data-stu-id="9432e-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="9432e-105">您可以指定`Protected Friend`只能在类; 的成员上不能应用`Protected Friend`为结构成员的因为结构不能被继承。</span><span class="sxs-lookup"><span data-stu-id="9432e-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="9432e-106">在 Visual Studio 中，选择上的 F1 帮助`protected friend`提供有关可以帮助[受保护](protected.md)或[友元](friend.md)。</span><span class="sxs-lookup"><span data-stu-id="9432e-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="9432e-107">IDE 选取单个令牌在光标，而不是组合词。</span><span class="sxs-lookup"><span data-stu-id="9432e-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="9432e-108">规则</span><span class="sxs-lookup"><span data-stu-id="9432e-108">Rules</span></span>

- <span data-ttu-id="9432e-109">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="9432e-109">**Declaration Context.**</span></span> <span data-ttu-id="9432e-110">可以使用`Protected Friend`仅在类级别。</span><span class="sxs-lookup"><span data-stu-id="9432e-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="9432e-111">这意味着声明上下文`Protected`元素必须是类，且不能为源文件、 命名空间、 接口、 模块、 结构或过程。</span><span class="sxs-lookup"><span data-stu-id="9432e-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="9432e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9432e-112">See also</span></span>

- [<span data-ttu-id="9432e-113">Public</span><span class="sxs-lookup"><span data-stu-id="9432e-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="9432e-114">Protected</span><span class="sxs-lookup"><span data-stu-id="9432e-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="9432e-115">Friend</span><span class="sxs-lookup"><span data-stu-id="9432e-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="9432e-116">Private</span><span class="sxs-lookup"><span data-stu-id="9432e-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="9432e-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="9432e-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="9432e-118">在 Visual Basic 中的访问级别</span><span class="sxs-lookup"><span data-stu-id="9432e-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="9432e-119">过程</span><span class="sxs-lookup"><span data-stu-id="9432e-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="9432e-120">结构</span><span class="sxs-lookup"><span data-stu-id="9432e-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="9432e-121">对象和类</span><span class="sxs-lookup"><span data-stu-id="9432e-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
