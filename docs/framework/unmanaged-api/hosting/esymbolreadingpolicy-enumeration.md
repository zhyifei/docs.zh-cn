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
ms.openlocfilehash: 28f6bdbc3e382f82b7fdd632b9fc8c4d422629c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429723"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="6c454-102">ESymbolReadingPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="6c454-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="6c454-103">包含将读取程序数据库 (PDB) 文件的策略设置的值。</span><span class="sxs-lookup"><span data-stu-id="6c454-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c454-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c454-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="6c454-105">成员</span><span class="sxs-lookup"><span data-stu-id="6c454-105">Members</span></span>  
  
|<span data-ttu-id="6c454-106">成员</span><span class="sxs-lookup"><span data-stu-id="6c454-106">Member</span></span>|<span data-ttu-id="6c454-107">描述</span><span class="sxs-lookup"><span data-stu-id="6c454-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="6c454-108">指定调试器应始终阅读 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="6c454-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="6c454-109">指定调试器应读取与完全信任程序集关联的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="6c454-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="6c454-110">指定调试器应永远不会读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="6c454-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c454-111">备注</span><span class="sxs-lookup"><span data-stu-id="6c454-111">Remarks</span></span>  
 <span data-ttu-id="6c454-112">`ESymbolReadingPolicy`枚举用于[iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6c454-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c454-113">要求</span><span class="sxs-lookup"><span data-stu-id="6c454-113">Requirements</span></span>  
 <span data-ttu-id="6c454-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c454-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c454-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6c454-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6c454-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c454-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c454-117">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c454-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c454-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c454-118">See Also</span></span>  
 [<span data-ttu-id="6c454-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="6c454-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
