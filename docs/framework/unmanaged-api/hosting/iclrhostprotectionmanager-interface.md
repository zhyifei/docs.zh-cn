---
title: ICLRHostProtectionManager 接口
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177770"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="956d2-102">ICLRHostProtectionManager 接口</span><span class="sxs-lookup"><span data-stu-id="956d2-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="956d2-103">使宿主能够阻止特定的托管的类、 方法、 属性和字段从部分受信任的代码中运行。</span><span class="sxs-lookup"><span data-stu-id="956d2-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="956d2-104">方法</span><span class="sxs-lookup"><span data-stu-id="956d2-104">Methods</span></span>  
  
|<span data-ttu-id="956d2-105">方法</span><span class="sxs-lookup"><span data-stu-id="956d2-105">Method</span></span>|<span data-ttu-id="956d2-106">描述</span><span class="sxs-lookup"><span data-stu-id="956d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="956d2-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="956d2-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="956d2-108">提供保证，将永远不会出现某些罕见的争用条件可能导致严重的公共语言运行时 (CLR) 错误。</span><span class="sxs-lookup"><span data-stu-id="956d2-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="956d2-109">SetProtectedCategories 方法</span><span class="sxs-lookup"><span data-stu-id="956d2-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="956d2-110">指定的托管的类型和成员应禁止在部分受信任的代码中运行的类别。</span><span class="sxs-lookup"><span data-stu-id="956d2-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="956d2-111">要求</span><span class="sxs-lookup"><span data-stu-id="956d2-111">Requirements</span></span>  
 <span data-ttu-id="956d2-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="956d2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="956d2-113">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="956d2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="956d2-114">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="956d2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="956d2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="956d2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956d2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="956d2-116">See also</span></span>

- [<span data-ttu-id="956d2-117">EApiCategories 枚举</span><span class="sxs-lookup"><span data-stu-id="956d2-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="956d2-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="956d2-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
