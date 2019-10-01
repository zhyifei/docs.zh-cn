---
title: 没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员
ms.date: 07/20/2015
f1_keywords:
- vbc30369
- bc30369
helpviewer_keywords:
- Shared
- BC30369
ms.assetid: 39d9466b-c1f3-4406-91a5-3d6c52d23a3d
ms.openlocfilehash: a2a5ab99ff68e6dce783a2fd986ee6e8c15ae858
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701164"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="01f3d-102">没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员</span><span class="sxs-lookup"><span data-stu-id="01f3d-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="01f3d-103">您尝试从共享过程中引用类的非共享成员。</span><span class="sxs-lookup"><span data-stu-id="01f3d-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="01f3d-104">下面的示例演示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="01f3d-104">The following example demonstrates such a situation.</span></span>  
  
```vb  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="01f3d-105">在前面的示例中，赋值语句 `x = 10` 将生成此错误消息。</span><span class="sxs-lookup"><span data-stu-id="01f3d-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="01f3d-106">这是因为共享过程尝试访问实例变量。</span><span class="sxs-lookup"><span data-stu-id="01f3d-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="01f3d-107">变量 `x` 是实例成员，因为它未声明为[Shared](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="01f3d-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="01f3d-108">类 @no__t 的每个实例都包含其自身 `x` 的单独变量。</span><span class="sxs-lookup"><span data-stu-id="01f3d-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="01f3d-109">当一个实例设置或更改 `x` 的值时，它不会影响任何其他实例中 `x` 的值。</span><span class="sxs-lookup"><span data-stu-id="01f3d-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="01f3d-110">但是，在 `sample` 类的所有实例中，步骤 `setX` @no__t。</span><span class="sxs-lookup"><span data-stu-id="01f3d-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="01f3d-111">这意味着它不与类的任何一个实例关联，而是独立于单个实例进行操作。</span><span class="sxs-lookup"><span data-stu-id="01f3d-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="01f3d-112">由于它与特定实例没有连接，因此 `setX` 无法访问实例变量。</span><span class="sxs-lookup"><span data-stu-id="01f3d-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="01f3d-113">它只能在 `Shared` 变量上运行。</span><span class="sxs-lookup"><span data-stu-id="01f3d-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="01f3d-114">@No__t 设置或更改共享变量的值时，该新值可供类的所有实例使用。</span><span class="sxs-lookup"><span data-stu-id="01f3d-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="01f3d-115">**错误 ID：** BC30369</span><span class="sxs-lookup"><span data-stu-id="01f3d-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="01f3d-116">更正此错误</span><span class="sxs-lookup"><span data-stu-id="01f3d-116">To correct this error</span></span>  
  
1. <span data-ttu-id="01f3d-117">确定是要在类的所有实例之间共享成员还是为每个实例保留单个成员。</span><span class="sxs-lookup"><span data-stu-id="01f3d-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="01f3d-118">如果希望在所有实例之间共享成员的单个副本，请将 @no__t 关键字添加到成员声明。</span><span class="sxs-lookup"><span data-stu-id="01f3d-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="01f3d-119">在过程声明中保留 `Shared` 关键字。</span><span class="sxs-lookup"><span data-stu-id="01f3d-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="01f3d-120">如果希望每个实例都有自己的成员的单独副本，请不要为成员声明指定 `Shared`。</span><span class="sxs-lookup"><span data-stu-id="01f3d-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="01f3d-121">删除过程声明中的 @no__t 0 关键字。</span><span class="sxs-lookup"><span data-stu-id="01f3d-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f3d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="01f3d-122">See also</span></span>

- [<span data-ttu-id="01f3d-123">Shared</span><span class="sxs-lookup"><span data-stu-id="01f3d-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
