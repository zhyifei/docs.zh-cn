---
title: "ESymbolReadingPolicy 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ESymbolReadingPolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ESymbolReadingPolicy
helpviewer_keywords: ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fdb18a343f91e85619f6d62e466fdd558044727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="2fad7-102">ESymbolReadingPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="2fad7-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="2fad7-103">包含将读取程序数据库 (PDB) 文件的策略设置的值。</span><span class="sxs-lookup"><span data-stu-id="2fad7-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fad7-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fad7-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="2fad7-105">成员</span><span class="sxs-lookup"><span data-stu-id="2fad7-105">Members</span></span>  
  
|<span data-ttu-id="2fad7-106">成员</span><span class="sxs-lookup"><span data-stu-id="2fad7-106">Member</span></span>|<span data-ttu-id="2fad7-107">描述</span><span class="sxs-lookup"><span data-stu-id="2fad7-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="2fad7-108">指定调试器应始终阅读 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="2fad7-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="2fad7-109">指定调试器应读取与完全信任程序集关联的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="2fad7-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="2fad7-110">指定调试器应永远不会读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="2fad7-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fad7-111">备注</span><span class="sxs-lookup"><span data-stu-id="2fad7-111">Remarks</span></span>  
 <span data-ttu-id="2fad7-112">`ESymbolReadingPolicy`枚举用于[iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2fad7-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fad7-113">惠?</span><span class="sxs-lookup"><span data-stu-id="2fad7-113">Requirements</span></span>  
 <span data-ttu-id="2fad7-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fad7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fad7-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fad7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fad7-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2fad7-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fad7-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fad7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fad7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fad7-118">See Also</span></span>  
 [<span data-ttu-id="2fad7-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="2fad7-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
