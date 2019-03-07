---
title: ICLRStrongName::StrongNameHashSize 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d246e3046cda9031689e625a0c3b054cbcf9f6e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465941"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="95c1d-102">ICLRStrongName::StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="95c1d-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="95c1d-103">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="95c1d-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95c1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="95c1d-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95c1d-105">参数</span><span class="sxs-lookup"><span data-stu-id="95c1d-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="95c1d-106">[in]用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="95c1d-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="95c1d-107">[out]返回的缓冲区大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="95c1d-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95c1d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="95c1d-108">Return Value</span></span>  
 <span data-ttu-id="95c1d-109">`S_OK` 如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="95c1d-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95c1d-110">要求</span><span class="sxs-lookup"><span data-stu-id="95c1d-110">Requirements</span></span>  
 <span data-ttu-id="95c1d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95c1d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95c1d-112">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="95c1d-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="95c1d-113">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="95c1d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95c1d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95c1d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95c1d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="95c1d-115">See also</span></span>
- [<span data-ttu-id="95c1d-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="95c1d-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
