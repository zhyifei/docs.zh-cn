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
ms.openlocfilehash: aad068b5857eb956ded63fa2a57cb163d3cf5c58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013837"
---
# <a name="cannot-refer-to-an-instance-member-of-a-class-from-within-a-shared-method-or-shared-member-initializer-without-an-explicit-instance-of-the-class"></a><span data-ttu-id="d53cc-102">没有类的显式实例，就无法从共享方法或共享成员初始值设定项中引用该类的实例成员</span><span class="sxs-lookup"><span data-stu-id="d53cc-102">Cannot refer to an instance member of a class from within a shared method or shared member initializer without an explicit instance of the class</span></span>
<span data-ttu-id="d53cc-103">已尝试对从共享的过程中的类的非共享成员，请参阅。</span><span class="sxs-lookup"><span data-stu-id="d53cc-103">You have tried to refer to a non-shared member of a class from within a shared procedure.</span></span> <span data-ttu-id="d53cc-104">下面的示例演示了这种情况。</span><span class="sxs-lookup"><span data-stu-id="d53cc-104">The following example demonstrates such a situation.</span></span>  
  
```  
Class sample  
    Public x as Integer  
    Public Shared Sub setX()  
        x = 10  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="d53cc-105">在前面的示例中，在赋值语句`x = 10`生成此错误消息。</span><span class="sxs-lookup"><span data-stu-id="d53cc-105">In the preceding example, the assignment statement `x = 10` generates this error message.</span></span> <span data-ttu-id="d53cc-106">这是因为共享的过程尝试访问的实例变量。</span><span class="sxs-lookup"><span data-stu-id="d53cc-106">This is because a shared procedure is attempting to access an instance variable.</span></span>  
  
 <span data-ttu-id="d53cc-107">在变量`x`是一个实例成员，因为它未声明为[共享](../../../visual-basic/language-reference/modifiers/shared.md)。</span><span class="sxs-lookup"><span data-stu-id="d53cc-107">The variable `x` is an instance member because it is not declared as [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="d53cc-108">类的每个实例`sample`包含其自己单独的变量`x`。</span><span class="sxs-lookup"><span data-stu-id="d53cc-108">Each instance of class `sample` contains its own individual variable `x`.</span></span> <span data-ttu-id="d53cc-109">一个实例时设置或更改的值`x`，它不会影响的值`x`中任何其他实例。</span><span class="sxs-lookup"><span data-stu-id="d53cc-109">When one instance sets or changes the value of `x`, it does not affect the value of `x` in any other instance.</span></span>  
  
 <span data-ttu-id="d53cc-110">但是，该过程`setX`是`Shared`类的所有实例之间`sample`。</span><span class="sxs-lookup"><span data-stu-id="d53cc-110">However, the procedure `setX` is `Shared` among all instances of class `sample`.</span></span> <span data-ttu-id="d53cc-111">这意味着它不与任何一个类的实例，但而不是独立于单个实例进行操作。</span><span class="sxs-lookup"><span data-stu-id="d53cc-111">This means it is not associated with any one instance of the class, but rather operates independently of individual instances.</span></span> <span data-ttu-id="d53cc-112">因为它具有与特定实例，没有连接`setX`无法访问一个实例变量。</span><span class="sxs-lookup"><span data-stu-id="d53cc-112">Because it has no connection with a particular instance, `setX` cannot access an instance variable.</span></span> <span data-ttu-id="d53cc-113">它必须仅在运行`Shared`变量。</span><span class="sxs-lookup"><span data-stu-id="d53cc-113">It must operate only on `Shared` variables.</span></span> <span data-ttu-id="d53cc-114">当`setX`设置或更改的新值为可用于类的所有实例的共享变量的值。</span><span class="sxs-lookup"><span data-stu-id="d53cc-114">When `setX` sets or changes the value of a shared variable, that new value is available to all instances of the class.</span></span>  
  
 <span data-ttu-id="d53cc-115">**错误 ID:** BC30369</span><span class="sxs-lookup"><span data-stu-id="d53cc-115">**Error ID:** BC30369</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d53cc-116">更正此错误</span><span class="sxs-lookup"><span data-stu-id="d53cc-116">To correct this error</span></span>  
  
1. <span data-ttu-id="d53cc-117">决定要在类的所有实例间共享或保留单独为每个实例的成员。</span><span class="sxs-lookup"><span data-stu-id="d53cc-117">Decide whether you want the member to be shared among all instances of the class, or kept individual for each instance.</span></span>  
  
2. <span data-ttu-id="d53cc-118">如果你想要在所有实例间共享的成员的一个副本，添加`Shared`向成员声明关键字。</span><span class="sxs-lookup"><span data-stu-id="d53cc-118">If you want a single copy of the member to be shared among all instances, add the `Shared` keyword to the member declaration.</span></span> <span data-ttu-id="d53cc-119">保留`Shared`过程声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d53cc-119">Retain the `Shared` keyword in the procedure declaration.</span></span>  
  
3. <span data-ttu-id="d53cc-120">如果您希望每个实例具有其自己的成员的单独副本，未指定`Shared`成员声明。</span><span class="sxs-lookup"><span data-stu-id="d53cc-120">If you want each instance to have its own individual copy of the member, do not specify `Shared` for the member declaration.</span></span> <span data-ttu-id="d53cc-121">删除`Shared`过程声明中的关键字。</span><span class="sxs-lookup"><span data-stu-id="d53cc-121">Remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53cc-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="d53cc-122">See also</span></span>

- [<span data-ttu-id="d53cc-123">Shared</span><span class="sxs-lookup"><span data-stu-id="d53cc-123">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
