---
title: "ICLRStrongName::StrongNameKeyGenEx 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyGenEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 581f486a2def90f44c0fb3f1bcf9d3bbcc1fc317
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="7a2e2-102">ICLRStrongName::StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="7a2e2-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="7a2e2-103">生成与指定的密钥大小，供强名称使用新的公钥/私钥密钥对。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a2e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a2e2-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7a2e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a2e2-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7a2e2-106">[in]请求的密钥容器名称中。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-106">[in] The requested key container name.</span></span> <span data-ttu-id="7a2e2-107">`wszKeyContainer`必须非空字符串或 null，以生成一个临时名称。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7a2e2-108">[in]一个值，指定是否保留注册密钥。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="7a2e2-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="7a2e2-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="7a2e2-110">0x00000000-时使用`wszKeyContainer`为 null 来生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="7a2e2-111">0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="7a2e2-112">[in]请求的密钥，以位为单位的密钥的大小。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="7a2e2-113">[out]返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="7a2e2-114">[out]大小，以字节为单位的`ppbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a2e2-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7a2e2-115">Return Value</span></span>  
 <span data-ttu-id="7a2e2-116">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a2e2-117">备注</span><span class="sxs-lookup"><span data-stu-id="7a2e2-117">Remarks</span></span>  
 <span data-ttu-id="7a2e2-118">.NET framework 1.0 和 1.1 版需要`dwKeySize`1024 位，强名称; 程序集进行签名的版本 2.0 添加为 2048年位密钥的支持。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="7a2e2-119">检索到密钥后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a2e2-120">惠?</span><span class="sxs-lookup"><span data-stu-id="7a2e2-120">Requirements</span></span>  
 <span data-ttu-id="7a2e2-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a2e2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a2e2-122">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7a2e2-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7a2e2-123">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7a2e2-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a2e2-124">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a2e2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a2e2-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a2e2-125">See Also</span></span>  
 [<span data-ttu-id="7a2e2-126">StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="7a2e2-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)  
 [<span data-ttu-id="7a2e2-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7a2e2-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
