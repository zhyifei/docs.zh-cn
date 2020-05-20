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
ms.openlocfilehash: 933edf734a0e02b4ac9c88d9f193277d963adada
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615789"
---
# <a name="iclrdebugmanagergetdacl-method"></a><span data-ttu-id="f5699-102">ICLRDebugManager::GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="f5699-102">ICLRDebugManager::GetDacl Method</span></span>
<span data-ttu-id="f5699-103">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="f5699-103">This method is not implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5699-104">语法</span><span class="sxs-lookup"><span data-stu-id="f5699-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDacl (  
    [out] PACL* ppacl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5699-105">参数</span><span class="sxs-lookup"><span data-stu-id="f5699-105">Parameters</span></span>  
 `ppacl`  
 <span data-ttu-id="f5699-106">弄访问控制列表（ACL）的接口指针。</span><span class="sxs-lookup"><span data-stu-id="f5699-106">[out] An interface pointer to the Access Control List (ACL).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f5699-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f5699-107">Return Value</span></span>  
  
|<span data-ttu-id="f5699-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f5699-108">HRESULT</span></span>|<span data-ttu-id="f5699-109">说明</span><span class="sxs-lookup"><span data-stu-id="f5699-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f5699-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f5699-110">E_NOTIMPL</span></span>|<span data-ttu-id="f5699-111">该方法未实现。</span><span class="sxs-lookup"><span data-stu-id="f5699-111">The method is not implemented.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5699-112">要求</span><span class="sxs-lookup"><span data-stu-id="f5699-112">Requirements</span></span>  
 <span data-ttu-id="f5699-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5699-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5699-114">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f5699-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5699-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f5699-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5699-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5699-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5699-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5699-117">See also</span></span>

- [<span data-ttu-id="f5699-118">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="f5699-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="f5699-119">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="f5699-119">ICLRDebugManager Interface</span></span>](iclrdebugmanager-interface.md)
- [<span data-ttu-id="f5699-120">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="f5699-120">SetDacl Method</span></span>](iclrdebugmanager-setdacl-method.md)
- [<span data-ttu-id="f5699-121">IHostControl 接口</span><span class="sxs-lookup"><span data-stu-id="f5699-121">IHostControl Interface</span></span>](ihostcontrol-interface.md)
