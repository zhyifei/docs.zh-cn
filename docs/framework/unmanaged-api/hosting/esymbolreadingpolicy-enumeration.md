---
title: ESymbolReadingPolicy 枚举
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b6b8593331801dd237d0a730afbd5a6a714bbf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774176"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="19382-102">ESymbolReadingPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="19382-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="19382-103">包含读取程序数据库 (PDB) 文件的策略设置的值。</span><span class="sxs-lookup"><span data-stu-id="19382-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19382-104">语法</span><span class="sxs-lookup"><span data-stu-id="19382-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="19382-105">成员</span><span class="sxs-lookup"><span data-stu-id="19382-105">Members</span></span>  
  
|<span data-ttu-id="19382-106">成员</span><span class="sxs-lookup"><span data-stu-id="19382-106">Member</span></span>|<span data-ttu-id="19382-107">描述</span><span class="sxs-lookup"><span data-stu-id="19382-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="19382-108">指定调试器应始终读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="19382-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="19382-109">指定调试器应读取与完全信任程序集相关联的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="19382-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="19382-110">指定调试器应永远不会读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="19382-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19382-111">备注</span><span class="sxs-lookup"><span data-stu-id="19382-111">Remarks</span></span>  
 <span data-ttu-id="19382-112">`ESymbolReadingPolicy`枚举用于[iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="19382-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19382-113">要求</span><span class="sxs-lookup"><span data-stu-id="19382-113">Requirements</span></span>  
 <span data-ttu-id="19382-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="19382-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19382-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="19382-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19382-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="19382-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19382-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19382-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19382-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="19382-118">See also</span></span>

- [<span data-ttu-id="19382-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="19382-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
