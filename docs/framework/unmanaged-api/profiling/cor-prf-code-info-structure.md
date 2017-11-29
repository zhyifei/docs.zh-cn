---
title: "COR_PRF_CODE_INFO 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_CODE_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_CODE_INFO
helpviewer_keywords: COR_PRF_CODE_INFO structure [.NET Framework profiling]
ms.assetid: cf30e27c-1f7e-43a2-ba1e-01e4137301db
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 007bb5990ec750dccc678a208d755136ea67a05c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corprfcodeinfo-structure"></a><span data-ttu-id="3eb74-102">COR_PRF_CODE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="3eb74-102">COR_PRF_CODE_INFO Structure</span></span>
<span data-ttu-id="3eb74-103">表示存储在内存中的一个本机代码连续块。</span><span class="sxs-lookup"><span data-stu-id="3eb74-103">Represents one contiguous block of native code stored in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eb74-104">语法</span><span class="sxs-lookup"><span data-stu-id="3eb74-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_CODE_INFO {  
    UINT_PTR startAddress;  
    SIZE_T size;  
} COR_PRF_CODE_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3eb74-105">成员</span><span class="sxs-lookup"><span data-stu-id="3eb74-105">Members</span></span>  
  
|<span data-ttu-id="3eb74-106">成员</span><span class="sxs-lookup"><span data-stu-id="3eb74-106">Member</span></span>|<span data-ttu-id="3eb74-107">描述</span><span class="sxs-lookup"><span data-stu-id="3eb74-107">Description</span></span>|  
|------------|-----------------|  
|`startAddress`|<span data-ttu-id="3eb74-108">代码连续块起始地址。</span><span class="sxs-lookup"><span data-stu-id="3eb74-108">The starting address of the contiguous block of code.</span></span>|  
|`size`|<span data-ttu-id="3eb74-109">块的大小。</span><span class="sxs-lookup"><span data-stu-id="3eb74-109">The size of the block.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3eb74-110">要求</span><span class="sxs-lookup"><span data-stu-id="3eb74-110">Requirements</span></span>  
 <span data-ttu-id="3eb74-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3eb74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eb74-112">**标头：** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="3eb74-112">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3eb74-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eb74-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eb74-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eb74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb74-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3eb74-115">See Also</span></span>  
 [<span data-ttu-id="3eb74-116">分析结构</span><span class="sxs-lookup"><span data-stu-id="3eb74-116">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
