---
title: "EApiCategories 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 630a3048072ed7b19b3250e75aca3b31e4dd7df7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="eapicategories-enumeration"></a><span data-ttu-id="afe98-102">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="afe98-102">EApiCategories Enumeration</span></span>
<span data-ttu-id="afe98-103">描述了主机可以阻止其运行部分受信任代码中的功能的类别。</span><span class="sxs-lookup"><span data-stu-id="afe98-103">Describes the categories of capabilities that the host can block from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe98-104">语法</span><span class="sxs-lookup"><span data-stu-id="afe98-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="afe98-105">成员</span><span class="sxs-lookup"><span data-stu-id="afe98-105">Members</span></span>  
  
|<span data-ttu-id="afe98-106">成员</span><span class="sxs-lookup"><span data-stu-id="afe98-106">Member</span></span>|<span data-ttu-id="afe98-107">描述</span><span class="sxs-lookup"><span data-stu-id="afe98-107">Description</span></span>|  
|------------|-----------------|  
|`eAll`|<span data-ttu-id="afe98-108">指定所有托管类和成员均覆盖由其他`EApiCategories`字段无法在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-108">Specifies that all managed classes and members that are covered by other `EApiCategories` fields be blocked from running in partially trusted code.</span></span>|  
|`eExternalProcessMgmt`|<span data-ttu-id="afe98-109">指定托管的类和成员允许创建、 操作以及外部进程析构禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-109">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external processes be blocked from running in partially trusted code.</span></span>|  
|`eExternalThreading`|<span data-ttu-id="afe98-110">指定托管的类和成员允许创建、 操作以及销毁外部线程的阻止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-110">Specifies that managed classes and members that allow the creation, manipulation, and destruction of external threads be blocked from running in partially trusted code.</span></span>|  
|`eMayLeakOnAbort`|<span data-ttu-id="afe98-111">指定托管的类型和成员无法可能泄漏内存中止禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-111">Specifies that managed types and members that could potentially leak memory on abort be blocked from running in partially trusted code.</span></span>|  
|`eNoCategory`|<span data-ttu-id="afe98-112">指定阻止在部分受信任的代码中运行任何托管的代码类别。</span><span class="sxs-lookup"><span data-stu-id="afe98-112">Specifies that no managed code categories be blocked from running in partially trusted code.</span></span>|  
|`eSecurityInfrastructure`|<span data-ttu-id="afe98-113">指定阻止被部分受信任的代码所使用公共语言运行时 (CLR) 安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="afe98-113">Specifies that the common language runtime (CLR) security infrastructure be blocked from being used by partially trusted code.</span></span>|  
|`eSelfAffectingProcessMgmt`|<span data-ttu-id="afe98-114">指定托管的类和成员其功能可能会影响托管的进程禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-114">Specifies that managed classes and members whose capabilities can affect the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSelfAffectingThreading`|<span data-ttu-id="afe98-115">指定托管的类和成员其功能可能会影响托管的进程中的线程禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-115">Specifies that managed classes and members whose capabilities can affect threads in the hosted process be blocked from running in partially trusted code.</span></span>|  
|`eSharedState`|<span data-ttu-id="afe98-116">指定托管的类和公开共享的状态的成员禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-116">Specifies that managed classes and members that expose shared state be blocked from running in partially trusted code.</span></span>|  
|`eSynchronization`|<span data-ttu-id="afe98-117">指定公共语言运行时类和成员，允许用户代码持有的锁禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-117">Specifies that common language runtime classes and members that allow user code to hold locks be blocked from running in partially trusted code.</span></span>|  
|`eUI`|<span data-ttu-id="afe98-118">指定托管的类和成员，允许，或是需要人工交互禁止在部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="afe98-118">Specifies that managed classes and members that allow or require human interaction be blocked from running in partially trusted code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afe98-119">备注</span><span class="sxs-lookup"><span data-stu-id="afe98-119">Remarks</span></span>  
 <span data-ttu-id="afe98-120">[Iclrhostprotectionmanager:: Setprotectedcategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)方法采用一个参数类型`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="afe98-120">The [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) method takes a parameter of type `EApiCategories`.</span></span>  
  
 <span data-ttu-id="afe98-121">`EApiCategories`枚举和`SetProtectedCategories`方法直接相关于托管<xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType>类。</span><span class="sxs-lookup"><span data-stu-id="afe98-121">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="afe98-122">托管的类用于<xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>枚举，其值直接对应`EApiCategories`值，来标记托管的类型和公开对应于所描述的类别的功能的成员`EApiCategories`。</span><span class="sxs-lookup"><span data-stu-id="afe98-122">The managed class is used with the <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeration, whose values correspond directly to the `EApiCategories` values, to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afe98-123">惠?</span><span class="sxs-lookup"><span data-stu-id="afe98-123">Requirements</span></span>  
 <span data-ttu-id="afe98-124">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afe98-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afe98-125">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="afe98-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afe98-126">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="afe98-126">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afe98-127">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afe98-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe98-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="afe98-128">See Also</span></span>  
 [<span data-ttu-id="afe98-129">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="afe98-129">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [<span data-ttu-id="afe98-130">承载枚举</span><span class="sxs-lookup"><span data-stu-id="afe98-130">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
