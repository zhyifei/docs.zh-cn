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
ms.openlocfilehash: c417bd883e2df2b5ae7984df9d8d21eaf7f87623
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434195"
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="35a82-102">ICLRDebugManager::GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="35a82-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="35a82-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="35a82-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35a82-104">语法</span><span class="sxs-lookup"><span data-stu-id="35a82-104">Syntax</span></span>  
  
```  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35a82-105">参数</span><span class="sxs-lookup"><span data-stu-id="35a82-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="35a82-106">[out]接口指针到访问控制列表 (ACL)。</span><span class="sxs-lookup"><span data-stu-id="35a82-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35a82-107">返回值</span><span class="sxs-lookup"><span data-stu-id="35a82-107">Return Value</span></span>  
  
|<span data-ttu-id="35a82-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35a82-108">HRESULT</span></span>|<span data-ttu-id="35a82-109">描述</span><span class="sxs-lookup"><span data-stu-id="35a82-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35a82-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="35a82-110">E_NOTIMPL</span></span>|<span data-ttu-id="35a82-111">未实现方法。</span><span class="sxs-lookup"><span data-stu-id="35a82-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35a82-112">要求</span><span class="sxs-lookup"><span data-stu-id="35a82-112">Requirements</span></span>  
 <span data-ttu-id="35a82-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35a82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35a82-114">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35a82-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35a82-115">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="35a82-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35a82-116">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35a82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a82-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="35a82-117">See Also</span></span>  
 [<span data-ttu-id="35a82-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="35a82-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="35a82-119">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="35a82-119">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="35a82-120">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="35a82-120">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)  
 [<span data-ttu-id="35a82-121">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="35a82-121">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
