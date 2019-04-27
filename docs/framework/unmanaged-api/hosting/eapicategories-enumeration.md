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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906368"
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="dcf61-102">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="dcf61-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="dcf61-103">介绍主机可以阻止其运行部分受信任的代码中的功能的类别。</span><span class="sxs-lookup"><span data-stu-id="dcf61-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcf61-104">语法</span><span class="sxs-lookup"><span data-stu-id="dcf61-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="dcf61-105">成员</span><span class="sxs-lookup"><span data-stu-id="dcf61-105">Members</span></span>  
  
|<span data-ttu-id="dcf61-106">成员</span><span class="sxs-lookup"><span data-stu-id="dcf61-106">Member</span></span>|<span data-ttu-id="dcf61-107">描述</span><span class="sxs-lookup"><span data-stu-id="dcf61-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="dcf61-108">指定所有托管类和成员受其他`EApiCategories`字段无法在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="dcf61-109">指定托管的类和成员允许创建、 操作和析构的外部进程的阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="dcf61-110">指定托管的类和成员允许创建、 操作和销毁外部线程的阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="dcf61-111">指定托管的类型和成员可能会泄漏内存在异常终止阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="dcf61-112">指定阻止在部分受信任的代码中运行任何托管的代码类别。</span><span class="sxs-lookup"><span data-stu-id="dcf61-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="dcf61-113">指定阻止正由部分受信任代码公共语言运行时 (CLR) 安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="dcf61-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="dcf61-114">指定托管的类和成员的功能可能会影响托管的进程阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="dcf61-115">指定托管的类和成员的功能可能会影响托管进程中的线程阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="dcf61-116">指定托管的类和成员公开共享的状态阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="dcf61-117">指定公共语言运行时类和成员，允许用户代码持有锁阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="dcf61-118">指定托管的类和成员允许或要求人机交互禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="dcf61-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dcf61-119">备注</span><span class="sxs-lookup"><span data-stu-id="dcf61-119">Remarks</span></span>  
 <span data-ttu-id="dcf61-120">[Iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法采用一个参数类型`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="dcf61-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="dcf61-121">`EApiCategories`枚举并`SetProtectedCategories`方法并直接关系到托管<xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="dcf61-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="dcf61-122">用于托管的类<xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>枚举，其值直接对应`EApiCategories`值，若要将标记公开功能与通过所述的类别相对应的托管的类型和成员`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="dcf61-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcf61-123">要求</span><span class="sxs-lookup"><span data-stu-id="dcf61-123">Requirements</span></span>  
 <span data-ttu-id="dcf61-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dcf61-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcf61-125">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dcf61-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dcf61-126">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dcf61-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dcf61-127">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcf61-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf61-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="dcf61-128">See also</span></span>

- [<span data-ttu-id="dcf61-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="dcf61-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="dcf61-130">承载枚举</span><span class="sxs-lookup"><span data-stu-id="dcf61-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
