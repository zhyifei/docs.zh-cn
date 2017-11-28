---
title: "ICLRStrongName::StrongNameKeyGen 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGen
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 13eef3e4c0cf4aa8de55aa96335e570ef1985e9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="e688c-102">ICLRStrongName::StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="e688c-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="e688c-103">创建强名称使用新的公钥/私钥密钥对。</span><span class="sxs-lookup"><span data-stu-id="e688c-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e688c-104">语法</span><span class="sxs-lookup"><span data-stu-id="e688c-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e688c-105">参数</span><span class="sxs-lookup"><span data-stu-id="e688c-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="e688c-106">[in]请求的密钥容器名称中。</span><span class="sxs-lookup"><span data-stu-id="e688c-106">[in] The requested key container name.</span></span> <span data-ttu-id="e688c-107">`wszKeyContainer`必须非空字符串或 null，以生成一个临时名称。</span><span class="sxs-lookup"><span data-stu-id="e688c-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e688c-108">[in]一个值，指定是否保留注册密钥。</span><span class="sxs-lookup"><span data-stu-id="e688c-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="e688c-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="e688c-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="e688c-110">0x00000000-时使用`wszKeyContainer`为 null 来生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="e688c-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="e688c-111">0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。</span><span class="sxs-lookup"><span data-stu-id="e688c-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="e688c-112">[out]返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="e688c-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="e688c-113">[out]大小，以字节为单位的`ppbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="e688c-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e688c-114">返回值</span><span class="sxs-lookup"><span data-stu-id="e688c-114">Return Value</span></span>  
 <span data-ttu-id="e688c-115">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="e688c-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e688c-116">备注</span><span class="sxs-lookup"><span data-stu-id="e688c-116">Remarks</span></span>  
 <span data-ttu-id="e688c-117">[Iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法创建一个 1024年位密钥。</span><span class="sxs-lookup"><span data-stu-id="e688c-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="e688c-118">检索到密钥后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e688c-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e688c-119">要求</span><span class="sxs-lookup"><span data-stu-id="e688c-119">Requirements</span></span>  
 <span data-ttu-id="e688c-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e688c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e688c-121">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e688c-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e688c-122">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e688c-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e688c-123">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e688c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e688c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e688c-124">See Also</span></span>  
 [<span data-ttu-id="e688c-125">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="e688c-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)  
 [<span data-ttu-id="e688c-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e688c-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
