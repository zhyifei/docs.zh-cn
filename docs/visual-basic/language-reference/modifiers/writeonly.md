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
ms.openlocfilehash: 163ec17f3ea96744290c54a73054ab132f842127
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647656"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="56e08-102">WriteOnly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56e08-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="56e08-103">指定可写入但无法读取属性。</span><span class="sxs-lookup"><span data-stu-id="56e08-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56e08-104">备注</span><span class="sxs-lookup"><span data-stu-id="56e08-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="56e08-105">规则</span><span class="sxs-lookup"><span data-stu-id="56e08-105">Rules</span></span>  
 <span data-ttu-id="56e08-106">**声明上下文。**</span><span class="sxs-lookup"><span data-stu-id="56e08-106">**Declaration Context.**</span></span> <span data-ttu-id="56e08-107">只能在模块级别使用 `WriteOnly`。</span><span class="sxs-lookup"><span data-stu-id="56e08-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="56e08-108">这意味着声明上下文`WriteOnly`属性必须是类、 结构或模块，并且不能是源文件、 命名空间或过程。</span><span class="sxs-lookup"><span data-stu-id="56e08-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="56e08-109">您可以将属性声明为`WriteOnly`，但不是变量。</span><span class="sxs-lookup"><span data-stu-id="56e08-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="56e08-110">何时使用 WriteOnly</span><span class="sxs-lookup"><span data-stu-id="56e08-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="56e08-111">有时您希望使用的代码，以便能够设置一个值，但不是会发现它是什么。</span><span class="sxs-lookup"><span data-stu-id="56e08-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="56e08-112">例如，敏感数据，如身份证号或密码，需要从访问由未设置任何组件进行保护。</span><span class="sxs-lookup"><span data-stu-id="56e08-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="56e08-113">在这些情况下，你可以使用`WriteOnly`属性设置的值。</span><span class="sxs-lookup"><span data-stu-id="56e08-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="56e08-114">当你定义并使用`WriteOnly`属性，请考虑以下附加保护措施：</span><span class="sxs-lookup"><span data-stu-id="56e08-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="56e08-115">**重写。**</span><span class="sxs-lookup"><span data-stu-id="56e08-115">**Overriding.**</span></span> <span data-ttu-id="56e08-116">如果该属性是类的成员，允许其默认为[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)，并不声明`Overridable`或`MustOverride`。</span><span class="sxs-lookup"><span data-stu-id="56e08-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="56e08-117">这可以防止不需要访问通过重写派生的类。</span><span class="sxs-lookup"><span data-stu-id="56e08-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="56e08-118">**访问级别。**</span><span class="sxs-lookup"><span data-stu-id="56e08-118">**Access Level.**</span></span> <span data-ttu-id="56e08-119">如果在一个或多个变量中保存该属性的敏感数据，将其声明[专用](../../../visual-basic/language-reference/modifiers/private.md)以便没有其他代码可以访问它们。</span><span class="sxs-lookup"><span data-stu-id="56e08-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="56e08-120">**加密。**</span><span class="sxs-lookup"><span data-stu-id="56e08-120">**Encryption.**</span></span> <span data-ttu-id="56e08-121">将所有敏感数据存储以加密形式，而不是以纯文本。</span><span class="sxs-lookup"><span data-stu-id="56e08-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="56e08-122">如果恶意代码以某种方式获得该内存区域的访问权，则更难以进行使用的数据。</span><span class="sxs-lookup"><span data-stu-id="56e08-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="56e08-123">加密也是很有用，如有必要进行序列化的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="56e08-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="56e08-124">**正在重置。**</span><span class="sxs-lookup"><span data-stu-id="56e08-124">**Resetting.**</span></span> <span data-ttu-id="56e08-125">类、 结构或将属性定义的模块时被终止，默认值或其他无意义的值重置的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="56e08-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="56e08-126">这提供额外的保护时进行常规访问时释放该内存区域。</span><span class="sxs-lookup"><span data-stu-id="56e08-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="56e08-127">**持久性。**</span><span class="sxs-lookup"><span data-stu-id="56e08-127">**Persistence.**</span></span> <span data-ttu-id="56e08-128">如果可以避免，则不保留任何敏感数据，例如在磁盘上。</span><span class="sxs-lookup"><span data-stu-id="56e08-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="56e08-129">此外，任何敏感数据写入剪贴板。</span><span class="sxs-lookup"><span data-stu-id="56e08-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="56e08-130">`WriteOnly`修饰符可用于在此上下文中：</span><span class="sxs-lookup"><span data-stu-id="56e08-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="56e08-131">Property 语句</span><span class="sxs-lookup"><span data-stu-id="56e08-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="56e08-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="56e08-132">See also</span></span>

- [<span data-ttu-id="56e08-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="56e08-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="56e08-134">Private</span><span class="sxs-lookup"><span data-stu-id="56e08-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="56e08-135">关键字</span><span class="sxs-lookup"><span data-stu-id="56e08-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
