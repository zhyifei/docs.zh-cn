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
ms.openlocfilehash: 0ebf2e0225cf497a0b89a46ecdb3e203d5b9a4cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432009"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="61361-102">ICLRStrongName::StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="61361-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="61361-103">获取使用指定的哈希算法的哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="61361-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61361-104">语法</span><span class="sxs-lookup"><span data-stu-id="61361-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61361-105">参数</span><span class="sxs-lookup"><span data-stu-id="61361-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="61361-106">[in]用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="61361-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="61361-107">[out]返回的缓冲区大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="61361-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61361-108">返回值</span><span class="sxs-lookup"><span data-stu-id="61361-108">Return Value</span></span>  
 <span data-ttu-id="61361-109">`S_OK` 如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="61361-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61361-110">要求</span><span class="sxs-lookup"><span data-stu-id="61361-110">Requirements</span></span>  
 <span data-ttu-id="61361-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61361-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61361-112">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="61361-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="61361-113">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="61361-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61361-114">**.NET framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61361-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61361-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="61361-115">See Also</span></span>  
 [<span data-ttu-id="61361-116">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="61361-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
