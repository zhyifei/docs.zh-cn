---
title: ICLRStrongName::StrongNameFreeBuffer 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82da60fc7ce5356c240a179529b9be4f621b2238
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494919"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="ab350-102">ICLRStrongName::StrongNameFreeBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="ab350-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="ab350-103">释放通过以前调用的强名称方法如分配的内存[iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)， [iclrstrongname:: Strongnametokenfrompublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)，或[Iclrstrongname:: Strongnamesignaturegeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)。</span><span class="sxs-lookup"><span data-stu-id="ab350-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab350-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab350-104">Syntax</span></span>  
  
```  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab350-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab350-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="ab350-106">[in]指向要释放的内存的指针。</span><span class="sxs-lookup"><span data-stu-id="ab350-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab350-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ab350-107">Return Value</span></span>  
 <span data-ttu-id="ab350-108">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="ab350-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab350-109">要求</span><span class="sxs-lookup"><span data-stu-id="ab350-109">Requirements</span></span>  
 <span data-ttu-id="ab350-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab350-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab350-111">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ab350-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab350-112">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ab350-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab350-113">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab350-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab350-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab350-114">See also</span></span>
- [<span data-ttu-id="ab350-115">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ab350-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
