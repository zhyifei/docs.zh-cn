---
title: ICLRDebugManager::GetDacl 方法
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.GetDacl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::GetDacl
helpviewer_keywords:
- GetDacl method [.NET Framework hosting]
- ICLRDebugManager::GetDacl method [.NET Framework hosting]
ms.assetid: 7115e920-aaff-440a-824e-39497139c6f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b19d6e43783211698ae2e68868aff87c91cc3e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773137"
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="1ad23-102">ICLRDebugManager::GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="1ad23-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="1ad23-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="1ad23-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ad23-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ad23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ad23-105">参数</span><span class="sxs-lookup"><span data-stu-id="1ad23-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="1ad23-106">[out]接口指针到访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="1ad23-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ad23-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1ad23-107">Return Value</span></span>  
  
|<span data-ttu-id="1ad23-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ad23-108">HRESULT</span></span>|<span data-ttu-id="1ad23-109">描述</span><span class="sxs-lookup"><span data-stu-id="1ad23-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ad23-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1ad23-110">E_NOTIMPL</span></span>|<span data-ttu-id="1ad23-111">未实现方法。</span><span class="sxs-lookup"><span data-stu-id="1ad23-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ad23-112">要求</span><span class="sxs-lookup"><span data-stu-id="1ad23-112">Requirements</span></span>  
 <span data-ttu-id="1ad23-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1ad23-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ad23-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ad23-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ad23-115">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1ad23-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ad23-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ad23-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ad23-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad23-117">See also</span></span>

- [<span data-ttu-id="1ad23-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="1ad23-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="1ad23-119">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="1ad23-119">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [<span data-ttu-id="1ad23-120">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="1ad23-120">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)
- [<span data-ttu-id="1ad23-121">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="1ad23-121">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
