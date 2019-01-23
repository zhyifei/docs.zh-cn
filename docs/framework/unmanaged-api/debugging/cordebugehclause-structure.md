---
title: CorDebugEHClause 结构
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be5d580c28a15a58cad6c5a2231d3a87e25c0e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495340"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="b2764-102">CorDebugEHClause 结构</span><span class="sxs-lookup"><span data-stu-id="b2764-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="b2764-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="b2764-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b2764-104">表示给定的一段中间语言 (IL) 代码的异常处理 (EH) 子句。</span><span class="sxs-lookup"><span data-stu-id="b2764-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2764-105">语法</span><span class="sxs-lookup"><span data-stu-id="b2764-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="b2764-106">成员</span><span class="sxs-lookup"><span data-stu-id="b2764-106">Members</span></span>  
  
|<span data-ttu-id="b2764-107">成员</span><span class="sxs-lookup"><span data-stu-id="b2764-107">Member</span></span>|<span data-ttu-id="b2764-108">描述</span><span class="sxs-lookup"><span data-stu-id="b2764-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="b2764-109">描述 EH 子句中的异常信息的位字段。</span><span class="sxs-lookup"><span data-stu-id="b2764-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="b2764-110">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="b2764-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="b2764-111">方法主体开头的 `try` 块的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b2764-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="b2764-112">`try` 块的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b2764-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="b2764-113">此 `try` 块的处理程序的位置。</span><span class="sxs-lookup"><span data-stu-id="b2764-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="b2764-114">处理程序代码的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b2764-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="b2764-115">基于类型的异常处理程序的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b2764-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="b2764-116">基于筛选器的异常处理程序的方法主体开头的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b2764-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2764-117">备注</span><span class="sxs-lookup"><span data-stu-id="b2764-117">Remarks</span></span>  
 <span data-ttu-id="b2764-118">一个数组`CoreDebugEHClause`返回的值[GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b2764-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="b2764-119">EH 子句信息由 CLI 规范定义。</span><span class="sxs-lookup"><span data-stu-id="b2764-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="b2764-120">有关详细信息，请参阅[标准 ECMA-355:公共语言基础结构 (CLI)，第 6 版](https://www.ecma-international.org/publications/standards/Ecma-335.htm)。</span><span class="sxs-lookup"><span data-stu-id="b2764-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="b2764-121">`flags` 字段可以包含以下标志。</span><span class="sxs-lookup"><span data-stu-id="b2764-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="b2764-122">请注意，它们不会在 CorDebug.idl 或 CorDebug.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="b2764-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="b2764-123">Flag</span><span class="sxs-lookup"><span data-stu-id="b2764-123">Flag</span></span>|<span data-ttu-id="b2764-124">值</span><span class="sxs-lookup"><span data-stu-id="b2764-124">Value</span></span>|<span data-ttu-id="b2764-125">描述</span><span class="sxs-lookup"><span data-stu-id="b2764-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="b2764-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b2764-126">0x00000000</span></span>|<span data-ttu-id="b2764-127">键入的异常子句。</span><span class="sxs-lookup"><span data-stu-id="b2764-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="b2764-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b2764-128">0x00000001</span></span>|<span data-ttu-id="b2764-129">异常筛选器和处理程序子句。</span><span class="sxs-lookup"><span data-stu-id="b2764-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="b2764-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b2764-130">0x00000002</span></span>|<span data-ttu-id="b2764-131">`finally` 子句。</span><span class="sxs-lookup"><span data-stu-id="b2764-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="b2764-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b2764-132">0x00000004</span></span>|<span data-ttu-id="b2764-133">Fault 子句（仅当引发异常时才调用的 `finally` 子句）。</span><span class="sxs-lookup"><span data-stu-id="b2764-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2764-134">要求</span><span class="sxs-lookup"><span data-stu-id="b2764-134">Requirements</span></span>  
 <span data-ttu-id="b2764-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2764-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2764-136">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2764-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2764-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2764-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2764-138">**.NET Framework 版本：**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2764-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2764-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2764-139">See also</span></span>
- [<span data-ttu-id="b2764-140">GetEHClauses 方法</span><span class="sxs-lookup"><span data-stu-id="b2764-140">GetEHClauses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="b2764-141">调试结构</span><span class="sxs-lookup"><span data-stu-id="b2764-141">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
