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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616224"
---
# <a name="einitializenewdomainflags-enumeration"></a><span data-ttu-id="16050-102">EInitializeNewDomainFlags 枚举</span><span class="sxs-lookup"><span data-stu-id="16050-102">EInitializeNewDomainFlags Enumeration</span></span>
<span data-ttu-id="16050-103">使宿主能够向运行时提供有关应用程序域初始化的信息。</span><span class="sxs-lookup"><span data-stu-id="16050-103">Enables the host to provide the runtime with information about the initialization of an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16050-104">语法</span><span class="sxs-lookup"><span data-stu-id="16050-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="16050-105">成员</span><span class="sxs-lookup"><span data-stu-id="16050-105">Members</span></span>  
  
|<span data-ttu-id="16050-106">成员</span><span class="sxs-lookup"><span data-stu-id="16050-106">Member</span></span>|<span data-ttu-id="16050-107">描述</span><span class="sxs-lookup"><span data-stu-id="16050-107">Description</span></span>|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|<span data-ttu-id="16050-108">无标志。</span><span class="sxs-lookup"><span data-stu-id="16050-108">No flags.</span></span>|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|<span data-ttu-id="16050-109">通知公共语言运行时（CLR）宿主不会在方法中更改应用程序域的安全状态 <xref:System.AppDomainManager.InitializeNewDomain%2A> 。</span><span class="sxs-lookup"><span data-stu-id="16050-109">Informs the common language runtime (CLR) that the host will not make changes to the security state of the application domain in the <xref:System.AppDomainManager.InitializeNewDomain%2A> method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16050-110">备注</span><span class="sxs-lookup"><span data-stu-id="16050-110">Remarks</span></span>  
 <span data-ttu-id="16050-111">[ICLRDomainManager：： SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)方法采用类型的参数 `EInitializeNewDomainFlags` 。</span><span class="sxs-lookup"><span data-stu-id="16050-111">The [ICLRDomainManager::SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) method takes a parameter of type `EInitializeNewDomainFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16050-112">要求</span><span class="sxs-lookup"><span data-stu-id="16050-112">Requirements</span></span>  
 <span data-ttu-id="16050-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="16050-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16050-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16050-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16050-115">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="16050-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16050-116">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16050-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16050-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16050-117">See also</span></span>

- [<span data-ttu-id="16050-118">承载枚举</span><span class="sxs-lookup"><span data-stu-id="16050-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="16050-119">SetAppDomainManagerType 方法</span><span class="sxs-lookup"><span data-stu-id="16050-119">SetAppDomainManagerType Method</span></span>](iclrdomainmanager-setappdomainmanagertype-method.md)
