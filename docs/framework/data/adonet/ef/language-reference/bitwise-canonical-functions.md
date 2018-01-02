---
title: "按位规范函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a4311b610859b36f1587e5e3f85e2a5f06503e1d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="bitwise-canonical-functions"></a><span data-ttu-id="99dcf-102">按位规范函数</span><span class="sxs-lookup"><span data-stu-id="99dcf-102">Bitwise Canonical Functions</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="99dcf-103"> 包含按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="99dcf-103"> includes bitwise canonical functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99dcf-104">备注</span><span class="sxs-lookup"><span data-stu-id="99dcf-104">Remarks</span></span>  
 <span data-ttu-id="99dcf-105">下表列出了 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="99dcf-105">The following table shows the bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span> <span data-ttu-id="99dcf-106">如果提供 `Null` 输入，则这些函数返回 `Null`。</span><span class="sxs-lookup"><span data-stu-id="99dcf-106">These functions will return `Null` if `Null` input is provided.</span></span> <span data-ttu-id="99dcf-107">这些函数的返回类型与自变量类型相同。</span><span class="sxs-lookup"><span data-stu-id="99dcf-107">The return type of the functions is the same as the argument type(s).</span></span> <span data-ttu-id="99dcf-108">如果函数采用多个自变量，则这些自变量必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="99dcf-108">Arguments must be of the same type, if the function takes more than one argument.</span></span> <span data-ttu-id="99dcf-109">若要对不同类型执行位运算，需要显式强制转换为同一类型。</span><span class="sxs-lookup"><span data-stu-id="99dcf-109">To perform bitwise operations across different types, you need to cast to the same type explicitly.</span></span>  
  
|<span data-ttu-id="99dcf-110">函数</span><span class="sxs-lookup"><span data-stu-id="99dcf-110">Function</span></span>|<span data-ttu-id="99dcf-111">描述</span><span class="sxs-lookup"><span data-stu-id="99dcf-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="99dcf-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="99dcf-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="99dcf-113">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位与结果。</span><span class="sxs-lookup"><span data-stu-id="99dcf-113">Returns the bitwise conjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="99dcf-114">**参数**</span><span class="sxs-lookup"><span data-stu-id="99dcf-114">**Arguments**</span></span><br /><br /> <span data-ttu-id="99dcf-115">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="99dcf-115">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="99dcf-116">**示例**</span><span class="sxs-lookup"><span data-stu-id="99dcf-116">**Example**</span></span><br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|<span data-ttu-id="99dcf-117">`BitWiseNot (` `value` `)`</span><span class="sxs-lookup"><span data-stu-id="99dcf-117">`BitWiseNot (` `value` `)`</span></span>|<span data-ttu-id="99dcf-118">返回 `value` 的位求反结果。</span><span class="sxs-lookup"><span data-stu-id="99dcf-118">Returns the bitwise negation of `value`.</span></span><br /><br /> <span data-ttu-id="99dcf-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="99dcf-119">**Arguments**</span></span><br /><br /> <span data-ttu-id="99dcf-120">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="99dcf-120">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="99dcf-121">**示例**</span><span class="sxs-lookup"><span data-stu-id="99dcf-121">**Example**</span></span><br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|<span data-ttu-id="99dcf-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="99dcf-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="99dcf-123">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位或结果。</span><span class="sxs-lookup"><span data-stu-id="99dcf-123">Returns the bitwise disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="99dcf-124">**参数**</span><span class="sxs-lookup"><span data-stu-id="99dcf-124">**Arguments**</span></span><br /><br /> <span data-ttu-id="99dcf-125">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="99dcf-125">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="99dcf-126">**示例**</span><span class="sxs-lookup"><span data-stu-id="99dcf-126">**Example**</span></span><br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|<span data-ttu-id="99dcf-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="99dcf-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="99dcf-128">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 位异或结果。</span><span class="sxs-lookup"><span data-stu-id="99dcf-128">Returns the bitwise exclusive disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="99dcf-129">**参数**</span><span class="sxs-lookup"><span data-stu-id="99dcf-129">**Arguments**</span></span><br /><br /> <span data-ttu-id="99dcf-130">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="99dcf-130">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="99dcf-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="99dcf-131">**Example**</span></span><br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a><span data-ttu-id="99dcf-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="99dcf-132">See Also</span></span>  
 [<span data-ttu-id="99dcf-133">规范函数</span><span class="sxs-lookup"><span data-stu-id="99dcf-133">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
