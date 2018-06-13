---
title: COR_PRF_FUNCTION_ARGUMENT_RANGE 结构
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_RANGE structure [.NET Framework profiling'
ms.assetid: 9f469eac-ac66-419b-8668-fe705bc1a51f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92e3a0a930a4e4b91cac27cbed1b745dea4207a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450019"
---
# <a name="corprffunctionargumentrange-structure"></a><span data-ttu-id="de9e4-102">COR_PRF_FUNCTION_ARGUMENT_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="de9e4-102">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>
<span data-ttu-id="de9e4-103">表示内存中按从左向右的顺序连续存储的函数自变量块。</span><span class="sxs-lookup"><span data-stu-id="de9e4-103">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de9e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="de9e4-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_RANGE {  
    UINT_PTR startAddress;  
    ULONG length;  
} COR_PRF_FUNCTION_ARGUMENT_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="de9e4-105">成员</span><span class="sxs-lookup"><span data-stu-id="de9e4-105">Members</span></span>  
  
|<span data-ttu-id="de9e4-106">成员</span><span class="sxs-lookup"><span data-stu-id="de9e4-106">Members</span></span>|<span data-ttu-id="de9e4-107">描述</span><span class="sxs-lookup"><span data-stu-id="de9e4-107">Description</span></span>|  
|-------------|-----------------|  
|`startAddress`|<span data-ttu-id="de9e4-108">块的起始地址。</span><span class="sxs-lookup"><span data-stu-id="de9e4-108">The starting address of the block.</span></span>|  
|`length`|<span data-ttu-id="de9e4-109">连续的块的长度。</span><span class="sxs-lookup"><span data-stu-id="de9e4-109">The length of the contiguous block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="de9e4-110">要求</span><span class="sxs-lookup"><span data-stu-id="de9e4-110">Requirements</span></span>  
 <span data-ttu-id="de9e4-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de9e4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de9e4-112">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="de9e4-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="de9e4-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de9e4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de9e4-114">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de9e4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9e4-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="de9e4-115">See Also</span></span>  
 [<span data-ttu-id="de9e4-116">分析结构</span><span class="sxs-lookup"><span data-stu-id="de9e4-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
