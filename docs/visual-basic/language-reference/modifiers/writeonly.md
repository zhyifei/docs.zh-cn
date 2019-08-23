---
title: WriteOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 43507ac8e9b5843e8fa9496737a3d77b3a425a7f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963772"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="e852f-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e852f-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="e852f-103">指定可以写入但不能读取属性。</span><span class="sxs-lookup"><span data-stu-id="e852f-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e852f-104">备注</span><span class="sxs-lookup"><span data-stu-id="e852f-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e852f-105">规则</span><span class="sxs-lookup"><span data-stu-id="e852f-105">Rules</span></span>  
 <span data-ttu-id="e852f-106">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="e852f-106">**Declaration Context.**</span></span> <span data-ttu-id="e852f-107">只能在模块级别使用 `WriteOnly`。</span><span class="sxs-lookup"><span data-stu-id="e852f-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="e852f-108">这意味着`WriteOnly`属性的声明上下文必须是类、结构或模块, 不能是源文件、命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="e852f-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="e852f-109">可以将属性声明为, `WriteOnly`但不能将变量声明为。</span><span class="sxs-lookup"><span data-stu-id="e852f-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="e852f-110">何时使用 WriteOnly</span><span class="sxs-lookup"><span data-stu-id="e852f-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="e852f-111">有时, 您希望使用的代码能够设置一个值, 但不会发现它是什么。</span><span class="sxs-lookup"><span data-stu-id="e852f-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="e852f-112">例如, 需要保护敏感数据 (例如社交注册号或密码) 不会被任何未设置的组件访问。</span><span class="sxs-lookup"><span data-stu-id="e852f-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="e852f-113">在这些情况下, 可以使用`WriteOnly`属性来设置值。</span><span class="sxs-lookup"><span data-stu-id="e852f-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e852f-114">定义和使用`WriteOnly`属性时, 请考虑下列附加保护措施:</span><span class="sxs-lookup"><span data-stu-id="e852f-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="e852f-115">**取代.**</span><span class="sxs-lookup"><span data-stu-id="e852f-115">**Overriding.**</span></span> <span data-ttu-id="e852f-116">如果该属性是类的成员, 则允许它默认为[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), 而不是将其`Overridable`声明为或。 `MustOverride`</span><span class="sxs-lookup"><span data-stu-id="e852f-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="e852f-117">这会阻止派生类通过重写进行不需要的访问。</span><span class="sxs-lookup"><span data-stu-id="e852f-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="e852f-118">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="e852f-118">**Access Level.**</span></span> <span data-ttu-id="e852f-119">如果将属性的敏感数据保存在一个或多个变量中, 请将它们声明为[私有](../../../visual-basic/language-reference/modifiers/private.md), 使其他代码都不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="e852f-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="e852f-120">**密匙.**</span><span class="sxs-lookup"><span data-stu-id="e852f-120">**Encryption.**</span></span> <span data-ttu-id="e852f-121">以加密形式而不是纯文本格式存储所有敏感数据。</span><span class="sxs-lookup"><span data-stu-id="e852f-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="e852f-122">如果恶意代码通过某种方式获得了对该内存区域的访问权限, 则更难使用数据。</span><span class="sxs-lookup"><span data-stu-id="e852f-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="e852f-123">如果需要序列化敏感数据, 则加密也很有用。</span><span class="sxs-lookup"><span data-stu-id="e852f-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="e852f-124">**重置.**</span><span class="sxs-lookup"><span data-stu-id="e852f-124">**Resetting.**</span></span> <span data-ttu-id="e852f-125">如果正在终止定义属性的类、结构或模块, 请将敏感数据重置为默认值或其他无意义的值。</span><span class="sxs-lookup"><span data-stu-id="e852f-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="e852f-126">这会在为常规访问释放内存区域时提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="e852f-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="e852f-127">**保持.**</span><span class="sxs-lookup"><span data-stu-id="e852f-127">**Persistence.**</span></span> <span data-ttu-id="e852f-128">如果可以避免任何敏感数据, 请不要将其保存在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="e852f-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="e852f-129">此外, 不要将任何敏感数据写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="e852f-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="e852f-130">可以在此上下文中使用修饰符:`WriteOnly`</span><span class="sxs-lookup"><span data-stu-id="e852f-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e852f-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="e852f-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e852f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e852f-132">See also</span></span>

- [<span data-ttu-id="e852f-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="e852f-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="e852f-134">Private</span><span class="sxs-lookup"><span data-stu-id="e852f-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="e852f-135">关键字</span><span class="sxs-lookup"><span data-stu-id="e852f-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
