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
ms.openlocfilehash: a20f9675af5a67291d95a9297b1ffa1c81a80522
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-canonical-functions"></a><span data-ttu-id="0aa04-102">按位规范函数</span><span class="sxs-lookup"><span data-stu-id="0aa04-102">Bitwise Canonical Functions</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="0aa04-103"> 包含按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="0aa04-103"> includes bitwise canonical functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0aa04-104">备注</span><span class="sxs-lookup"><span data-stu-id="0aa04-104">Remarks</span></span>  
 <span data-ttu-id="0aa04-105">下表列出了 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 按位规范函数。</span><span class="sxs-lookup"><span data-stu-id="0aa04-105">The following table shows the bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span> <span data-ttu-id="0aa04-106">如果提供 `Null` 输入，则这些函数返回 `Null`。</span><span class="sxs-lookup"><span data-stu-id="0aa04-106">These functions will return `Null` if `Null` input is provided.</span></span> <span data-ttu-id="0aa04-107">这些函数的返回类型与自变量类型相同。</span><span class="sxs-lookup"><span data-stu-id="0aa04-107">The return type of the functions is the same as the argument type(s).</span></span> <span data-ttu-id="0aa04-108">如果函数采用多个自变量，则这些自变量必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="0aa04-108">Arguments must be of the same type, if the function takes more than one argument.</span></span> <span data-ttu-id="0aa04-109">若要对不同类型执行位运算，需要显式强制转换为同一类型。</span><span class="sxs-lookup"><span data-stu-id="0aa04-109">To perform bitwise operations across different types, you need to cast to the same type explicitly.</span></span>  
  
|<span data-ttu-id="0aa04-110">函数</span><span class="sxs-lookup"><span data-stu-id="0aa04-110">Function</span></span>|<span data-ttu-id="0aa04-111">描述</span><span class="sxs-lookup"><span data-stu-id="0aa04-111">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0aa04-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="0aa04-112">`BitWiseAnd (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="0aa04-113">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位与结果。</span><span class="sxs-lookup"><span data-stu-id="0aa04-113">Returns the bitwise conjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="0aa04-114">**参数**</span><span class="sxs-lookup"><span data-stu-id="0aa04-114">**Arguments**</span></span><br /><br /> <span data-ttu-id="0aa04-115">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="0aa04-115">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="0aa04-116">**示例**</span><span class="sxs-lookup"><span data-stu-id="0aa04-116">**Example**</span></span><br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|<span data-ttu-id="0aa04-117">`BitWiseNot (` `value` `)`</span><span class="sxs-lookup"><span data-stu-id="0aa04-117">`BitWiseNot (` `value` `)`</span></span>|<span data-ttu-id="0aa04-118">返回 `value` 的位求反结果。</span><span class="sxs-lookup"><span data-stu-id="0aa04-118">Returns the bitwise negation of `value`.</span></span><br /><br /> <span data-ttu-id="0aa04-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="0aa04-119">**Arguments**</span></span><br /><br /> <span data-ttu-id="0aa04-120">A `Byte`， `Int16`， `Int32`，和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="0aa04-120">A `Byte`, `Int16`, `Int32`, and `Int64`.</span></span><br /><br /> <span data-ttu-id="0aa04-121">**示例**</span><span class="sxs-lookup"><span data-stu-id="0aa04-121">**Example**</span></span><br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|<span data-ttu-id="0aa04-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="0aa04-122">`BitWiseOr (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="0aa04-123">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 的位或结果。</span><span class="sxs-lookup"><span data-stu-id="0aa04-123">Returns the bitwise disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="0aa04-124">**参数**</span><span class="sxs-lookup"><span data-stu-id="0aa04-124">**Arguments**</span></span><br /><br /> <span data-ttu-id="0aa04-125">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="0aa04-125">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="0aa04-126">**示例**</span><span class="sxs-lookup"><span data-stu-id="0aa04-126">**Example**</span></span><br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|<span data-ttu-id="0aa04-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span><span class="sxs-lookup"><span data-stu-id="0aa04-127">`BitWiseXor (` `value1` `,`  `value2` `)`</span></span>|<span data-ttu-id="0aa04-128">按照 `value1` 和 `value2` 的类型返回 `value1` 和 `value2` 位异或结果。</span><span class="sxs-lookup"><span data-stu-id="0aa04-128">Returns the bitwise exclusive disjunction of `value1` and `value2` as the type of `value1` and `value2`.</span></span><br /><br /> <span data-ttu-id="0aa04-129">**参数**</span><span class="sxs-lookup"><span data-stu-id="0aa04-129">**Arguments**</span></span><br /><br /> <span data-ttu-id="0aa04-130">A `Byte`， `Int16`，`Int32`和`Int64`。</span><span class="sxs-lookup"><span data-stu-id="0aa04-130">A `Byte`, `Int16`, `Int32` and `Int64`.</span></span><br /><br /> <span data-ttu-id="0aa04-131">**示例**</span><span class="sxs-lookup"><span data-stu-id="0aa04-131">**Example**</span></span><br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a><span data-ttu-id="0aa04-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0aa04-132">See Also</span></span>  
 [<span data-ttu-id="0aa04-133">规范函数</span><span class="sxs-lookup"><span data-stu-id="0aa04-133">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
