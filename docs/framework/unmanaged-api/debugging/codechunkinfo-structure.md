---
title: CodeChunkInfo 结构
ms.date: 03/30/2017
api_name:
- CodeChunkInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CodeChunkInfo
helpviewer_keywords:
- CodeChunkInfo structure [.NET Framework debugging]
ms.assetid: 0f482454-8517-48de-ba7a-d7aedab13bb5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58c9d4c66af0bb9f4e66d17b18ac78ef8271bc31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072657"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="38629-102">CodeChunkInfo 结构</span><span class="sxs-lookup"><span data-stu-id="38629-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="38629-103">表示内存中的单一代码块。</span><span class="sxs-lookup"><span data-stu-id="38629-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38629-104">语法</span><span class="sxs-lookup"><span data-stu-id="38629-104">Syntax</span></span>  
  
```  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="38629-105">成员</span><span class="sxs-lookup"><span data-stu-id="38629-105">Members</span></span>  
  
|<span data-ttu-id="38629-106">成员</span><span class="sxs-lookup"><span data-stu-id="38629-106">Member</span></span>|<span data-ttu-id="38629-107">描述</span><span class="sxs-lookup"><span data-stu-id="38629-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="38629-108">一个`CORDB_ADDRESS`值，该值指定块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="38629-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="38629-109">以字节为单位的块区的大小。</span><span class="sxs-lookup"><span data-stu-id="38629-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38629-110">备注</span><span class="sxs-lookup"><span data-stu-id="38629-110">Remarks</span></span>  
 <span data-ttu-id="38629-111">单一代码块是本机代码的代码对象，例如函数的一部分的区域。</span><span class="sxs-lookup"><span data-stu-id="38629-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38629-112">要求</span><span class="sxs-lookup"><span data-stu-id="38629-112">Requirements</span></span>  
 <span data-ttu-id="38629-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38629-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38629-114">**标头：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="38629-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="38629-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38629-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="38629-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="38629-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38629-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="38629-117">See also</span></span>

- [<span data-ttu-id="38629-118">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="38629-118">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="38629-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="38629-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="38629-120">调试</span><span class="sxs-lookup"><span data-stu-id="38629-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
