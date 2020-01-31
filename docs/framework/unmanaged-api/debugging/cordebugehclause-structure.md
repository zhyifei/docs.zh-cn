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
ms.openlocfilehash: 197c33511a474eb8291e4361ebb3c21fb3720cae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789427"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="b0403-102">CorDebugEHClause 结构</span><span class="sxs-lookup"><span data-stu-id="b0403-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="b0403-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="b0403-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b0403-104">表示给定的一段中间语言 (IL) 代码的异常处理 (EH) 子句。</span><span class="sxs-lookup"><span data-stu-id="b0403-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0403-105">语法</span><span class="sxs-lookup"><span data-stu-id="b0403-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0403-106">Members</span><span class="sxs-lookup"><span data-stu-id="b0403-106">Members</span></span>  
  
|<span data-ttu-id="b0403-107">成员</span><span class="sxs-lookup"><span data-stu-id="b0403-107">Member</span></span>|<span data-ttu-id="b0403-108">描述</span><span class="sxs-lookup"><span data-stu-id="b0403-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="b0403-109">描述 EH 子句中的异常信息的位字段。</span><span class="sxs-lookup"><span data-stu-id="b0403-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="b0403-110">有关详细信息，请参阅“备注”部分。</span><span class="sxs-lookup"><span data-stu-id="b0403-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="b0403-111">方法主体开头的 `try` 块的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b0403-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="b0403-112">`try` 块的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b0403-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="b0403-113">此 `try` 块的处理程序的位置。</span><span class="sxs-lookup"><span data-stu-id="b0403-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="b0403-114">处理程序代码的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b0403-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="b0403-115">基于类型的异常处理程序的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="b0403-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="b0403-116">基于筛选器的异常处理程序的方法主体开头的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b0403-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0403-117">备注</span><span class="sxs-lookup"><span data-stu-id="b0403-117">Remarks</span></span>  
 <span data-ttu-id="b0403-118">[GetEHClauses](icordebugilcode-getehclauses-method.md)方法返回 `CoreDebugEHClause` 值的数组。</span><span class="sxs-lookup"><span data-stu-id="b0403-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="b0403-119">EH 子句信息由 CLI 规范定义。</span><span class="sxs-lookup"><span data-stu-id="b0403-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="b0403-120">有关详细信息，请参阅[标准 ECMA-355：公共语言基础结构（CLI）、第六版](https://www.ecma-international.org/publications/standards/Ecma-335.htm)。</span><span class="sxs-lookup"><span data-stu-id="b0403-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="b0403-121">`flags` 字段可以包含以下标志。</span><span class="sxs-lookup"><span data-stu-id="b0403-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="b0403-122">请注意，它们不会在 CorDebug.idl 或 CorDebug.h 中定义。</span><span class="sxs-lookup"><span data-stu-id="b0403-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="b0403-123">Flag</span><span class="sxs-lookup"><span data-stu-id="b0403-123">Flag</span></span>|<span data-ttu-id="b0403-124">{2&gt;值&lt;2}</span><span class="sxs-lookup"><span data-stu-id="b0403-124">Value</span></span>|<span data-ttu-id="b0403-125">描述</span><span class="sxs-lookup"><span data-stu-id="b0403-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="b0403-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="b0403-126">0x00000000</span></span>|<span data-ttu-id="b0403-127">键入的异常子句。</span><span class="sxs-lookup"><span data-stu-id="b0403-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="b0403-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="b0403-128">0x00000001</span></span>|<span data-ttu-id="b0403-129">异常筛选器和处理程序子句。</span><span class="sxs-lookup"><span data-stu-id="b0403-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="b0403-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="b0403-130">0x00000002</span></span>|<span data-ttu-id="b0403-131">`finally` 子句。</span><span class="sxs-lookup"><span data-stu-id="b0403-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="b0403-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="b0403-132">0x00000004</span></span>|<span data-ttu-id="b0403-133">Fault 子句（仅当引发异常时才调用的 `finally` 子句）。</span><span class="sxs-lookup"><span data-stu-id="b0403-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0403-134">需求</span><span class="sxs-lookup"><span data-stu-id="b0403-134">Requirements</span></span>  
 <span data-ttu-id="b0403-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b0403-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0403-136">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0403-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0403-137">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0403-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0403-138">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0403-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0403-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0403-139">See also</span></span>

- [<span data-ttu-id="b0403-140">GetEHClauses 方法</span><span class="sxs-lookup"><span data-stu-id="b0403-140">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="b0403-141">调试结构</span><span class="sxs-lookup"><span data-stu-id="b0403-141">Debugging Structures</span></span>](debugging-structures.md)
