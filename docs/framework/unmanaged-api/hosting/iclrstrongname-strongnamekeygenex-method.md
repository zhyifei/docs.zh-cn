---
title: ICLRStrongName::StrongNameKeyGenEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGenEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGenEx
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyGenEx method [.NET Framework hosting]
- StrongNameKeyGenEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 1f8b59d0-5b72-45b8-ab74-c2b43ffc806e
topic_type:
- apiref
ms.openlocfilehash: b09677a45c5d515aacb2cac709599140039a9dd8
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899558"
---
# <a name="iclrstrongnamestrongnamekeygenex-method"></a><span data-ttu-id="7a8d5-102">ICLRStrongName::StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="7a8d5-102">ICLRStrongName::StrongNameKeyGenEx Method</span></span>
<span data-ttu-id="7a8d5-103">使用指定的密钥大小生成新的公钥/私钥对，以便使用强名称。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-103">Generates a new public/private key pair with the specified key size, for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a8d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="7a8d5-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGenEx (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [in]  DWORD     dwKeySize,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a8d5-105">参数</span><span class="sxs-lookup"><span data-stu-id="7a8d5-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7a8d5-106">中请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-106">[in] The requested key container name.</span></span> <span data-ttu-id="7a8d5-107">`wszKeyContainer` 必须为非空字符串或 null，才能生成临时名称。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7a8d5-108">中一个值，该值指定是否保留注册的密钥。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="7a8d5-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="7a8d5-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="7a8d5-110">0x00000000-在 `wszKeyContainer` 为 null 时使用，以生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="7a8d5-111">0x00000001 （`SN_LEAVE_KEY`）-指定密钥应为 "已注册"。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `dwKeySize`  
 <span data-ttu-id="7a8d5-112">中请求的密钥大小，以位为单位。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-112">[in] The requested size of the key, in bits.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="7a8d5-113">弄返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-113">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="7a8d5-114">弄`ppbKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-114">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a8d5-115">返回值</span><span class="sxs-lookup"><span data-stu-id="7a8d5-115">Return Value</span></span>  
 <span data-ttu-id="7a8d5-116">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-116">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a8d5-117">备注</span><span class="sxs-lookup"><span data-stu-id="7a8d5-117">Remarks</span></span>  
 <span data-ttu-id="7a8d5-118">.NET Framework 版本1.0 和1.1 需要 `dwKeySize` 1024 位才能使用强名称为程序集签名;版本2.0 添加了对2048位密钥的支持。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-118">The .NET Framework versions 1.0 and 1.1 require a `dwKeySize` of 1024 bits to sign an assembly with a strong name; version 2.0 adds supports for 2048-bit keys.</span></span>  
  
 <span data-ttu-id="7a8d5-119">检索到密钥后，应调用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-119">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a8d5-120">需求</span><span class="sxs-lookup"><span data-stu-id="7a8d5-120">Requirements</span></span>  
 <span data-ttu-id="7a8d5-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7a8d5-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a8d5-122">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="7a8d5-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7a8d5-123">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7a8d5-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7a8d5-124">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a8d5-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a8d5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a8d5-125">See also</span></span>

- [<span data-ttu-id="7a8d5-126">StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="7a8d5-126">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="7a8d5-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7a8d5-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
