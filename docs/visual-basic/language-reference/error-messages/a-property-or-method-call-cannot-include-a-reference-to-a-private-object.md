---
title: 无论是作为参数还是作为返回值，属性或方法调用都不能包括对私有对象的引用
ms.date: 07/20/2015
f1_keywords:
- vbrID98
ms.assetid: 059b43e1-202d-4fa2-806b-7bad63c1e7ca
ms.openlocfilehash: 0a8d6603bf5c97b966d29f000b21435cec8040d8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840947"
---
# <a name="a-property-or-method-call-cannot-include-a-reference-to-a-private-object-either-as-an-argument-or-as-a-return-value"></a><span data-ttu-id="a00ef-102">无论是作为参数还是作为返回值，属性或方法调用都不能包括对私有对象的引用</span><span class="sxs-lookup"><span data-stu-id="a00ef-102">A property or method call cannot include a reference to a private object, either as an argument or as a return value</span></span>
<span data-ttu-id="a00ef-103">此错误的可能原因包括：</span><span class="sxs-lookup"><span data-stu-id="a00ef-103">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="a00ef-104">客户端调用了进程外组件的属性或方法，并且试图将对私有对象的引用作为参数之一进行传递。</span><span class="sxs-lookup"><span data-stu-id="a00ef-104">A client invoked a property or method of an out-of-process component and attempted to pass a reference to a private object as one of the arguments.</span></span>  
  
-   <span data-ttu-id="a00ef-105">进程外组件调用了其客户端上的回调方法，并试图传递对私有对象的引用。</span><span class="sxs-lookup"><span data-stu-id="a00ef-105">An out-of-process component invoked a call-back method on its client and attempted to pass a reference to a private object.</span></span>  
  
-   <span data-ttu-id="a00ef-106">进程外组件试图将对私有对象的引用作为它所引发的事件的参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="a00ef-106">An out-of-process component attempted to pass a reference to a private object as an argument of an event it was raising.</span></span>  
  
-   <span data-ttu-id="a00ef-107">客户端试图将私有对象引用赋给它正在处理的事件的 `ByRef` 参数。</span><span class="sxs-lookup"><span data-stu-id="a00ef-107">A client attempted to assign a private object reference to a `ByRef` argument of an event it was handling.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a00ef-108">更正此错误</span><span class="sxs-lookup"><span data-stu-id="a00ef-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="a00ef-109">删除引用。</span><span class="sxs-lookup"><span data-stu-id="a00ef-109">Remove the reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00ef-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a00ef-110">See also</span></span>

- [<span data-ttu-id="a00ef-111">Private</span><span class="sxs-lookup"><span data-stu-id="a00ef-111">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
