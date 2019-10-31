---
title: EApiCategories 枚举
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131216"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="27a4f-102">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="27a4f-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="27a4f-103">描述宿主可阻止在部分受信任代码中运行的功能类别。</span><span class="sxs-lookup"><span data-stu-id="27a4f-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="27a4f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a><span data-ttu-id="27a4f-105">Members</span><span class="sxs-lookup"><span data-stu-id="27a4f-105">Members</span></span>  
  
|<span data-ttu-id="27a4f-106">成员</span><span class="sxs-lookup"><span data-stu-id="27a4f-106">Member</span></span>|<span data-ttu-id="27a4f-107">描述</span><span class="sxs-lookup"><span data-stu-id="27a4f-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="27a4f-108">指定阻止其他 `EApiCategories` 字段覆盖的所有托管类和成员在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="27a4f-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="27a4f-109">指定禁止在部分受信任的代码中运行外部进程的创建、操作和析构的托管类和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="27a4f-110">指定允许在部分受信任的代码中阻止创建、操作和销毁外部线程的托管类和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="27a4f-111">指定在部分受信任的代码中阻止在中止时可能泄漏内存的托管类型和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="27a4f-112">指定禁止在部分受信任的代码中运行托管代码类别。</span><span class="sxs-lookup"><span data-stu-id="27a4f-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="27a4f-113">指定禁止部分受信任的代码使用公共语言运行时（CLR）安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="27a4f-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="27a4f-114">指定在部分受信任的代码中阻止其功能影响托管进程的托管类和成员运行。</span><span class="sxs-lookup"><span data-stu-id="27a4f-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="27a4f-115">指定在部分受信任的代码中阻止其功能影响托管进程中的线程的托管类和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="27a4f-116">指定阻止公开共享状态的托管类和成员在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="27a4f-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="27a4f-117">指定允许用户代码持有锁的公共语言运行时类和成员阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="27a4f-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="27a4f-118">指定在部分受信任的代码中阻止允许或要求人工交互的托管类和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27a4f-119">备注</span><span class="sxs-lookup"><span data-stu-id="27a4f-119">Remarks</span></span>  
 <span data-ttu-id="27a4f-120">[ICLRHostProtectionManager：： SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法使用 `EApiCategories`类型的参数。</span><span class="sxs-lookup"><span data-stu-id="27a4f-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="27a4f-121">`EApiCategories` 枚举和 `SetProtectedCategories` 方法与托管 <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> 类直接相关。</span><span class="sxs-lookup"><span data-stu-id="27a4f-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="27a4f-122">托管类与 <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> 枚举一起使用，其值直接对应于 `EApiCategories` 值，用于标记公开与 `EApiCategories`所述的类别对应的功能的托管类型和成员。</span><span class="sxs-lookup"><span data-stu-id="27a4f-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a4f-123">要求</span><span class="sxs-lookup"><span data-stu-id="27a4f-123">Requirements</span></span>  
 <span data-ttu-id="27a4f-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27a4f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a4f-125">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27a4f-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27a4f-126">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="27a4f-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27a4f-127">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27a4f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a4f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="27a4f-128">See also</span></span>

- [<span data-ttu-id="27a4f-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="27a4f-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="27a4f-130">承载枚举</span><span class="sxs-lookup"><span data-stu-id="27a4f-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
