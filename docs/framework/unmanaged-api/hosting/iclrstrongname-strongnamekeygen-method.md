---
title: ICLRStrongName::StrongNameKeyGen 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abeb731ecd66e4412f904b085abcfc7b5b3a3c4b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169775"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="82c0a-102">ICLRStrongName::StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="82c0a-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="82c0a-103">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="82c0a-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82c0a-104">语法</span><span class="sxs-lookup"><span data-stu-id="82c0a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82c0a-105">参数</span><span class="sxs-lookup"><span data-stu-id="82c0a-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="82c0a-106">[in]请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="82c0a-106">[in] The requested key container name.</span></span> `wszKeyContainer` <span data-ttu-id="82c0a-107">必须非空字符串或 null 可生成一个临时名称。</span><span class="sxs-lookup"><span data-stu-id="82c0a-107">must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="82c0a-108">[in]一个值，指定是否保留注册密钥。</span><span class="sxs-lookup"><span data-stu-id="82c0a-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="82c0a-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="82c0a-109">The following values are supported:</span></span>  
  
-   <span data-ttu-id="82c0a-110">0x00000000-时使用`wszKeyContainer`为 null 以生成一个临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="82c0a-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="82c0a-111">0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。</span><span class="sxs-lookup"><span data-stu-id="82c0a-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="82c0a-112">[out]返回的公共/专用密钥对。</span><span class="sxs-lookup"><span data-stu-id="82c0a-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="82c0a-113">[out]大小，以字节为单位的`ppbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="82c0a-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82c0a-114">返回值</span><span class="sxs-lookup"><span data-stu-id="82c0a-114">Return Value</span></span>  
 `S_OK` <span data-ttu-id="82c0a-115">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="82c0a-115">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82c0a-116">备注</span><span class="sxs-lookup"><span data-stu-id="82c0a-116">Remarks</span></span>  
 <span data-ttu-id="82c0a-117">[Iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法创建一个 1024年位密钥。</span><span class="sxs-lookup"><span data-stu-id="82c0a-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="82c0a-118">正在检索密钥后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法，以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="82c0a-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82c0a-119">要求</span><span class="sxs-lookup"><span data-stu-id="82c0a-119">Requirements</span></span>  
 <span data-ttu-id="82c0a-120">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82c0a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82c0a-121">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="82c0a-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="82c0a-122">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="82c0a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="82c0a-123">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="82c0a-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="82c0a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="82c0a-124">See also</span></span>

- [<span data-ttu-id="82c0a-125">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="82c0a-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="82c0a-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="82c0a-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
