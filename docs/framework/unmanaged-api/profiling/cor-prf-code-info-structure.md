---
title: COR_PRF_CODE_INFO 结构
ms.date: 03/30/2017
api_name:
- COR_PRF_CODE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CODE_INFO
helpviewer_keywords:
- COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e83dbb234cf1cacc0e18d4e42bccb427eb54f14c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54617247"
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="91a58-102">COR_PRF_CODE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="91a58-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="91a58-103">表示存储在内存中的一个本机代码连续块。</span><span class="sxs-lookup"><span data-stu-id="91a58-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a58-104">语法</span><span class="sxs-lookup"><span data-stu-id="91a58-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="91a58-105">成员</span><span class="sxs-lookup"><span data-stu-id="91a58-105">Members</span></span>  
  
|<span data-ttu-id="91a58-106">成员</span><span class="sxs-lookup"><span data-stu-id="91a58-106">Member</span></span>|<span data-ttu-id="91a58-107">描述</span><span class="sxs-lookup"><span data-stu-id="91a58-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="91a58-108">代码连续块起始地址。</span><span class="sxs-lookup"><span data-stu-id="91a58-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="91a58-109">块的大小。</span><span class="sxs-lookup"><span data-stu-id="91a58-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91a58-110">要求</span><span class="sxs-lookup"><span data-stu-id="91a58-110">Requirements</span></span>  
 <span data-ttu-id="91a58-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91a58-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a58-112">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="91a58-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="91a58-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91a58-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91a58-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a58-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a58-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="91a58-115">See also</span></span>
- [<span data-ttu-id="91a58-116">分析结构</span><span class="sxs-lookup"><span data-stu-id="91a58-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
