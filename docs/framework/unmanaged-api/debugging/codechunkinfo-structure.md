---
title: "CodeChunkInfo 结构 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CodeChunkInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: CodeChunkInfo
helpviewer_keywords: CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17727c8927f9db3de3ab26d2504dfae5215a1495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="codechunkinfo-structure1"></a><span data-ttu-id="72838-102">CodeChunkInfo 结构 1</span><span class="sxs-lookup"><span data-stu-id="72838-102">CodeChunkInfo Structure1</span></span>
<span data-ttu-id="72838-103">表示内存中的单一代码块。</span><span class="sxs-lookup"><span data-stu-id="72838-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72838-104">语法</span><span class="sxs-lookup"><span data-stu-id="72838-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="72838-105">成员</span><span class="sxs-lookup"><span data-stu-id="72838-105">Members</span></span>  
  
|<span data-ttu-id="72838-106">成员</span><span class="sxs-lookup"><span data-stu-id="72838-106">Member</span></span>|<span data-ttu-id="72838-107">描述</span><span class="sxs-lookup"><span data-stu-id="72838-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="72838-108">A`CORDB_ADDRESS`值，该值指定的块区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="72838-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="72838-109">以字节为单位，区块的大小。</span><span class="sxs-lookup"><span data-stu-id="72838-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72838-110">备注</span><span class="sxs-lookup"><span data-stu-id="72838-110">Remarks</span></span>  
 <span data-ttu-id="72838-111">的单一代码块是属于一个代码对象，如函数的本机代码的区域。</span><span class="sxs-lookup"><span data-stu-id="72838-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72838-112">要求</span><span class="sxs-lookup"><span data-stu-id="72838-112">Requirements</span></span>  
 <span data-ttu-id="72838-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72838-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72838-114">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="72838-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="72838-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72838-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72838-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72838-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72838-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72838-117">See Also</span></span>  
 [<span data-ttu-id="72838-118">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="72838-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 [<span data-ttu-id="72838-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="72838-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="72838-120">调试</span><span class="sxs-lookup"><span data-stu-id="72838-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
