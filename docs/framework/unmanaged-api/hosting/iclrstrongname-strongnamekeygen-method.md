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
ms.openlocfilehash: db5c0dbe57607c7a3bf8b97cee734415aa934336
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763080"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a><span data-ttu-id="91b75-102">ICLRStrongName::StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="91b75-102">ICLRStrongName::StrongNameKeyGen Method</span></span>
<span data-ttu-id="91b75-103">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="91b75-103">Creates a new public/private key pair for strong name use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b75-104">语法</span><span class="sxs-lookup"><span data-stu-id="91b75-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91b75-105">参数</span><span class="sxs-lookup"><span data-stu-id="91b75-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="91b75-106">中请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="91b75-106">[in] The requested key container name.</span></span> <span data-ttu-id="91b75-107">`wszKeyContainer`必须为非空字符串，或者为 null 以生成临时名称。</span><span class="sxs-lookup"><span data-stu-id="91b75-107">`wszKeyContainer` must either be a non-empty string or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="91b75-108">中一个值，该值指定是否保留注册的密钥。</span><span class="sxs-lookup"><span data-stu-id="91b75-108">[in] A value that specifies whether to leave the key registered.</span></span> <span data-ttu-id="91b75-109">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="91b75-109">The following values are supported:</span></span>  
  
- <span data-ttu-id="91b75-110">0x00000000-在 `wszKeyContainer` 为 null 时用于生成临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="91b75-110">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="91b75-111">0x00000001 （ `SN_LEAVE_KEY` ）-指定密钥应为 "已注册"。</span><span class="sxs-lookup"><span data-stu-id="91b75-111">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="91b75-112">弄返回的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="91b75-112">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="91b75-113">弄的大小（以字节为单位） `ppbKeyBlob` 。</span><span class="sxs-lookup"><span data-stu-id="91b75-113">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91b75-114">返回值</span><span class="sxs-lookup"><span data-stu-id="91b75-114">Return Value</span></span>  
 <span data-ttu-id="91b75-115">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="91b75-115">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91b75-116">注解</span><span class="sxs-lookup"><span data-stu-id="91b75-116">Remarks</span></span>  
 <span data-ttu-id="91b75-117">[ICLRStrongName：： StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法创建1024位键。</span><span class="sxs-lookup"><span data-stu-id="91b75-117">The [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method creates a 1024-bit key.</span></span> <span data-ttu-id="91b75-118">检索到密钥后，应调用[ICLRStrongName：： StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="91b75-118">After the key is retrieved, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91b75-119">要求</span><span class="sxs-lookup"><span data-stu-id="91b75-119">Requirements</span></span>  
 <span data-ttu-id="91b75-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91b75-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91b75-121">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="91b75-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="91b75-122">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="91b75-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91b75-123">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91b75-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b75-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91b75-124">See also</span></span>

- [<span data-ttu-id="91b75-125">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="91b75-125">StrongNameKeyGenEx Method</span></span>](iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="91b75-126">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="91b75-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
