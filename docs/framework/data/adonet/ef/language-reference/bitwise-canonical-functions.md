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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1d703b2467d508324f3eb39b822c239484ac1c6e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="bitwise-canonical-functions"></a><span data-ttu-id="e5453-102">按位规范函数</span><span class="sxs-lookup"><span data-stu-id="e5453-102">Bitwise Canonical Functions</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="e5453-103"> 包含按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="e5453-103"> includes bitwise canonical functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5453-104">备注</span><span class="sxs-lookup"><span data-stu-id="e5453-104">Remarks</span></span>  
 <span data-ttu-id="e5453-105">下表列出了 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="e5453-105">The following table shows the bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span> <span data-ttu-id="e5453-106">如果提供 `Null` 输入，则这些函数返回 `Null`。</span><span class="sxs-lookup"><span data-stu-id="e5453-106">These functions will return `Null` if `Null` input is provided.</span></span> <span data-ttu-id="e5453-107">这些函数的返回类型与自变量类型相同。</span><span class="sxs-lookup"><span data-stu-id="e5453-107">The return type of the functions is the same as the argument type(s).</span></span> <span data-ttu-id="e5453-108">如果函数采用多个自变量，则这些自变量必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="e5453-108">Arguments must be of the same type, if the function takes more than one argument.</span></span> <span data-ttu-id="e5453-109">若要对不同类型执行位运算，需要显式强制转换为同一类型。</span><span class="sxs-lookup"><span data-stu-id="e5453-109">To perform bitwise operations across different types, you need to cast to the same type explicitly.</span></span>  
  
|<span data-ttu-id="e5453-110">函数</span><span class="sxs-lookup"><span data-stu-id="e5453-110">Function</span></span>|<span data-ttu-id="e5453-111">描述</span><span class="sxs-lookup"><span data-stu-id="e5453-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="e5453-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="e5453-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="e5453-113">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位与结果。</span><span class="sxs-lookup"><span data-stu-id="e5453-113">Returns the bitwise conjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="e5453-114">**参数**</span><span class="sxs-lookup"><span data-stu-id="e5453-114">**Arguments**</span></span><br /><br /> <span data-ttu-id="e5453-115">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="e5453-115">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="e5453-116">**示例**</span><span class="sxs-lookup"><span data-stu-id="e5453-116">**Example**</span></span><br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|<span data-ttu-id="e5453-117">`BitWiseNot (` `value` `)`</span><span class="sxs-lookup"><span data-stu-id="e5453-117">`BitWiseNot (` `value` `)`</span></span>|<span data-ttu-id="e5453-118">返回 `value` 的位求反结果。</span><span class="sxs-lookup"><span data-stu-id="e5453-118">Returns the bitwise negation of `value`.</span></span><br /><br /> <span data-ttu-id="e5453-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="e5453-119">**Arguments**</span></span><br /><br /> <span data-ttu-id="e5453-120">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="e5453-120">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="e5453-121">**示例**</span><span class="sxs-lookup"><span data-stu-id="e5453-121">**Example**</span></span><br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|<span data-ttu-id="e5453-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="e5453-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="e5453-123">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位或结果。</span><span class="sxs-lookup"><span data-stu-id="e5453-123">Returns the bitwise disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="e5453-124">**参数**</span><span class="sxs-lookup"><span data-stu-id="e5453-124">**Arguments**</span></span><br /><br /> <span data-ttu-id="e5453-125">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="e5453-125">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="e5453-126">**示例**</span><span class="sxs-lookup"><span data-stu-id="e5453-126">**Example**</span></span><br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|<span data-ttu-id="e5453-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="e5453-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="e5453-128">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 位异或结果。</span><span class="sxs-lookup"><span data-stu-id="e5453-128">Returns the bitwise exclusive disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="e5453-129">**参数**</span><span class="sxs-lookup"><span data-stu-id="e5453-129">**Arguments**</span></span><br /><br /> <span data-ttu-id="e5453-130">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="e5453-130">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="e5453-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="e5453-131">**Example**</span></span><br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a><span data-ttu-id="e5453-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5453-132">See Also</span></span>  
 [<span data-ttu-id="e5453-133">规范函数</span><span class="sxs-lookup"><span data-stu-id="e5453-133">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
