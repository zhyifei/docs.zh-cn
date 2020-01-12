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
ms.openlocfilehash: e437ee2ab04d3b1126ec2911553e87586e74e54e
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899618"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="676e2-102">ICLRStrongName::StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="676e2-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="676e2-103">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="676e2-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="676e2-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="676e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="676e2-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="676e2-106">中请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="676e2-106">[in] The requested key container name.</span></span> <span data-ttu-id="676e2-107">`wszKeyContainer` 必须为非空字符串或 null，才能生成临时名称。</span><span class="sxs-lookup"><span data-stu-id="676e2-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="676e2-108">中一个值，该值指定是否保留注册的密钥。</span><span class="sxs-lookup"><span data-stu-id="676e2-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="676e2-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="676e2-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="676e2-110">0x00000000-在 `wszKeyContainer` 为 null 时使用，以生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="676e2-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="676e2-111">0x00000001 （`SN_LEAVE_KEY`）-指定密钥应为 "已注册"。</span><span class="sxs-lookup"><span data-stu-id="676e2-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="676e2-112">弄返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="676e2-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="676e2-113">弄`ppbKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="676e2-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="676e2-114">返回值</span><span class="sxs-lookup"><span data-stu-id="676e2-114">Return Value</span></span>  
 <span data-ttu-id="676e2-115">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="676e2-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="676e2-116">备注</span><span class="sxs-lookup"><span data-stu-id="676e2-116">Remarks</span></span>  
 <span data-ttu-id="676e2-117">[ICLRStrongName：： StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法创建1024位键。</span><span class="sxs-lookup"><span data-stu-id="676e2-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="676e2-118">检索到密钥后，应调用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="676e2-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="676e2-119">需求</span><span class="sxs-lookup"><span data-stu-id="676e2-119">Requirements</span></span>  
 <span data-ttu-id="676e2-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="676e2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676e2-121">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="676e2-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="676e2-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="676e2-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="676e2-123">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676e2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676e2-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="676e2-124">See also</span></span>

- [<span data-ttu-id="676e2-125">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="676e2-125">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="676e2-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="676e2-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
