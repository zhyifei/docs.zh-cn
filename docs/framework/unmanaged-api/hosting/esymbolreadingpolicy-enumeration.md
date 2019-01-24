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
ms.openlocfilehash: e17f88cf7f0d8572e65d00d8500a1fd83aa44eeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663909"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="865b6-102">ESymbolReadingPolicy 枚举</span><span class="sxs-lookup"><span data-stu-id="865b6-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="865b6-103">包含读取程序数据库 (PDB) 文件的策略设置的值。</span><span class="sxs-lookup"><span data-stu-id="865b6-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="865b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="865b6-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="865b6-105">成员</span><span class="sxs-lookup"><span data-stu-id="865b6-105">Members</span></span>  
  
|<span data-ttu-id="865b6-106">成员</span><span class="sxs-lookup"><span data-stu-id="865b6-106">Member</span></span>|<span data-ttu-id="865b6-107">描述</span><span class="sxs-lookup"><span data-stu-id="865b6-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="865b6-108">指定调试器应始终读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="865b6-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="865b6-109">指定调试器应读取与完全信任程序集相关联的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="865b6-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="865b6-110">指定调试器应永远不会读取 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="865b6-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="865b6-111">备注</span><span class="sxs-lookup"><span data-stu-id="865b6-111">Remarks</span></span>  
 <span data-ttu-id="865b6-112">`ESymbolReadingPolicy`枚举用于[iclrdebugmanager:: Setsymbolreadingpolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="865b6-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="865b6-113">要求</span><span class="sxs-lookup"><span data-stu-id="865b6-113">Requirements</span></span>  
 <span data-ttu-id="865b6-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="865b6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="865b6-115">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="865b6-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="865b6-116">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="865b6-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="865b6-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="865b6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="865b6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="865b6-118">See also</span></span>
- [<span data-ttu-id="865b6-119">承载枚举</span><span class="sxs-lookup"><span data-stu-id="865b6-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
