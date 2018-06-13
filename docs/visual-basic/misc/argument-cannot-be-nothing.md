---
title: 参数不能为 Nothing
ms.date: 07/20/2015
f1_keywords:
- vbrGeneral_ArgumentNullException
ms.assetid: 2abd995b-36a5-45f0-b3c1-6e0c3b31a875
ms.openlocfilehash: 7b08dd41f638138df4c2f92fbe9f05f1312c2d03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600056"
---
# <a name="argument-cannot-be-nothing"></a><span data-ttu-id="405d0-102">参数不能为 Nothing</span><span class="sxs-lookup"><span data-stu-id="405d0-102">Argument cannot be Nothing</span></span>
<span data-ttu-id="405d0-103">向必须具有值的参数提供了 null 值。</span><span class="sxs-lookup"><span data-stu-id="405d0-103">A null value has been supplied for an argument that must have a value.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="405d0-104">更正此错误</span><span class="sxs-lookup"><span data-stu-id="405d0-104">To correct this error</span></span>  
  
-   <span data-ttu-id="405d0-105">你可能试图在未先提供对象的实例的情况下使用对象。</span><span class="sxs-lookup"><span data-stu-id="405d0-105">You might have tried to use an object without providing an instance of the object.</span></span> <span data-ttu-id="405d0-106">在这种情况下，请使用 `New` 关键字创建实例。</span><span class="sxs-lookup"><span data-stu-id="405d0-106">In such a case, use the `New` keyword to create the instance.</span></span>  
  
-   <span data-ttu-id="405d0-107">检查值是否计算正确。</span><span class="sxs-lookup"><span data-stu-id="405d0-107">Check that the value is calculated correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="405d0-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="405d0-108">See Also</span></span>  
 <xref:System.NullReferenceException>
