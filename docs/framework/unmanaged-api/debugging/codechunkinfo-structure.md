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
ms.openlocfilehash: d33c8b31473e389e07fb24076dc32272e9dde387
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132391"
---
# <a name="codechunkinfo-structure"></a><span data-ttu-id="140da-102">CodeChunkInfo 结构</span><span class="sxs-lookup"><span data-stu-id="140da-102">CodeChunkInfo Structure</span></span>

<span data-ttu-id="140da-103">表示内存中的单一代码块。</span><span class="sxs-lookup"><span data-stu-id="140da-103">Represents a single chunk of code in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="140da-104">语法</span><span class="sxs-lookup"><span data-stu-id="140da-104">Syntax</span></span>  
  
```cpp  
typedef struct _CodeChunkInfo {  
    CORDB_ADDRESS startAddr;  
    ULONG32       length;  
} CodeChunkInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="140da-105">Members</span><span class="sxs-lookup"><span data-stu-id="140da-105">Members</span></span>  
  
|<span data-ttu-id="140da-106">成员</span><span class="sxs-lookup"><span data-stu-id="140da-106">Member</span></span>|<span data-ttu-id="140da-107">描述</span><span class="sxs-lookup"><span data-stu-id="140da-107">Description</span></span>|  
|------------|-----------------|  
|`startAddr`|<span data-ttu-id="140da-108">一个 `CORDB_ADDRESS` 值，该值指定块区的起始地址。</span><span class="sxs-lookup"><span data-stu-id="140da-108">A `CORDB_ADDRESS` value that specifies the starting address of the chunk.</span></span>|  
|`length`|<span data-ttu-id="140da-109">块区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="140da-109">The size, in bytes, of the chunk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="140da-110">备注</span><span class="sxs-lookup"><span data-stu-id="140da-110">Remarks</span></span>  
 <span data-ttu-id="140da-111">单个代码块是本机代码区域，它是代码对象（例如函数）的一部分。</span><span class="sxs-lookup"><span data-stu-id="140da-111">The single chunk of code is a region of native code that is part of a code object such as a function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="140da-112">要求</span><span class="sxs-lookup"><span data-stu-id="140da-112">Requirements</span></span>  
 <span data-ttu-id="140da-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="140da-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="140da-114">**标头：** Cordebug.idl .idl</span><span class="sxs-lookup"><span data-stu-id="140da-114">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="140da-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="140da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="140da-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="140da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="140da-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="140da-117">See also</span></span>

- [<span data-ttu-id="140da-118">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="140da-118">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)
- [<span data-ttu-id="140da-119">调试结构</span><span class="sxs-lookup"><span data-stu-id="140da-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="140da-120">调试</span><span class="sxs-lookup"><span data-stu-id="140da-120">Debugging</span></span>](index.md)
