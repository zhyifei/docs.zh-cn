---
title: "ICLRHostProtectionManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager
helpviewer_keywords: ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 37b1aaeef1d4c375f36ad043124287fc3b41e3fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="6de28-102">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="6de28-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="6de28-103">使主机可以阻止特定的托管的类、 方法、 属性和字段从部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="6de28-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6de28-104">方法</span><span class="sxs-lookup"><span data-stu-id="6de28-104">Methods</span></span>  
  
|<span data-ttu-id="6de28-105">方法</span><span class="sxs-lookup"><span data-stu-id="6de28-105">Method</span></span>|<span data-ttu-id="6de28-106">描述</span><span class="sxs-lookup"><span data-stu-id="6de28-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6de28-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="6de28-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="6de28-108">提供保证可能导致严重的公共语言运行时 (CLR) 错误某些罕见的争用情况将永远不会出现。</span><span class="sxs-lookup"><span data-stu-id="6de28-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="6de28-109">SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="6de28-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="6de28-110">指定托管的类型和成员，应禁止在部分受信任的代码中运行的类别。</span><span class="sxs-lookup"><span data-stu-id="6de28-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6de28-111">惠?</span><span class="sxs-lookup"><span data-stu-id="6de28-111">Requirements</span></span>  
 <span data-ttu-id="6de28-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6de28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de28-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6de28-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6de28-114">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6de28-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6de28-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de28-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6de28-116">See Also</span></span>  
 [<span data-ttu-id="6de28-117">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="6de28-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="6de28-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="6de28-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
