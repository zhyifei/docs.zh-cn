---
title: EInitializeNewDomainFlags 枚举
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129418"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="0e778-102">EInitializeNewDomainFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="0e778-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="0e778-103">使宿主能够向运行时提供有关应用程序域初始化的信息。</span><span class="sxs-lookup"><span data-stu-id="0e778-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e778-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e778-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0e778-105">Members</span><span class="sxs-lookup"><span data-stu-id="0e778-105">Members</span></span>  
  
|<span data-ttu-id="0e778-106">成员</span><span class="sxs-lookup"><span data-stu-id="0e778-106">Member</span></span>|<span data-ttu-id="0e778-107">描述</span><span class="sxs-lookup"><span data-stu-id="0e778-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="0e778-108">无标志。</span><span class="sxs-lookup"><span data-stu-id="0e778-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="0e778-109">通知公共语言运行时（CLR）宿主不会在 <xref:System.AppDomainManager.InitializeNewDomain%2A> 方法中更改应用程序域的安全状态。</span><span class="sxs-lookup"><span data-stu-id="0e778-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e778-110">备注</span><span class="sxs-lookup"><span data-stu-id="0e778-110">Remarks</span></span>  
 <span data-ttu-id="0e778-111">[ICLRDomainManager：： SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)方法使用 `EInitializeNewDomainFlags`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="0e778-111">The [ICLRDomainManager::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e778-112">要求</span><span class="sxs-lookup"><span data-stu-id="0e778-112">Requirements</span></span>  
 <span data-ttu-id="0e778-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e778-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e778-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0e778-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e778-115">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0e778-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e778-116">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e778-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e778-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e778-117">See also</span></span>

- [<span data-ttu-id="0e778-118">承载枚举</span><span class="sxs-lookup"><span data-stu-id="0e778-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="0e778-119">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="0e778-119">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
