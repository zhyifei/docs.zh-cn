---
title: StrongNameKeyGen 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30610311d2c48f15ebd85910557892784c0cfe85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542491"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="497cf-102">StrongNameKeyGen 函数</span><span class="sxs-lookup"><span data-stu-id="497cf-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="497cf-103">创建新的公钥/私钥对，以便强名称使用。</span><span class="sxs-lookup"><span data-stu-id="497cf-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="497cf-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="497cf-104">This function has been deprecated.</span></span> <span data-ttu-id="497cf-105">使用[iclrstrongname:: Strongnamekeygen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="497cf-105">Use the [ICLRStrongName::StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="497cf-106">语法</span><span class="sxs-lookup"><span data-stu-id="497cf-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="497cf-107">参数</span><span class="sxs-lookup"><span data-stu-id="497cf-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="497cf-108">[in]请求的密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="497cf-108">[in] The requested key container name.</span></span> <span data-ttu-id="497cf-109">`wszKeyContainer` 必须为非空字符串，或空值，以生成一个临时名称。</span><span class="sxs-lookup"><span data-stu-id="497cf-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="497cf-110">[in]指定是否保留注册密钥。</span><span class="sxs-lookup"><span data-stu-id="497cf-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="497cf-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="497cf-111">The following values are supported:</span></span>  
  
-   <span data-ttu-id="497cf-112">0x00000000-时使用`wszKeyContainer`为 null 以生成一个临时密钥容器名称。</span><span class="sxs-lookup"><span data-stu-id="497cf-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
-   <span data-ttu-id="497cf-113">0x00000001 (`SN_LEAVE_KEY`)-指定应保持注册密钥。</span><span class="sxs-lookup"><span data-stu-id="497cf-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="497cf-114">[out]返回的公共/专用密钥对。</span><span class="sxs-lookup"><span data-stu-id="497cf-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="497cf-115">[out]大小，以字节为单位的`ppbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="497cf-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="497cf-116">返回值</span><span class="sxs-lookup"><span data-stu-id="497cf-116">Return Value</span></span>  
 <span data-ttu-id="497cf-117">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="497cf-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="497cf-118">备注</span><span class="sxs-lookup"><span data-stu-id="497cf-118">Remarks</span></span>  
 <span data-ttu-id="497cf-119">`StrongNameKeyGen`函数创建的 1024年位密钥。</span><span class="sxs-lookup"><span data-stu-id="497cf-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="497cf-120">正在检索密钥后，应调用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数，以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="497cf-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="497cf-121">如果`StrongNameKeyGen`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="497cf-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="497cf-122">要求</span><span class="sxs-lookup"><span data-stu-id="497cf-122">Requirements</span></span>  
 <span data-ttu-id="497cf-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="497cf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="497cf-124">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="497cf-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="497cf-125">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="497cf-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="497cf-126">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="497cf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="497cf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="497cf-127">See also</span></span>
- [<span data-ttu-id="497cf-128">StrongNameKeyGen 方法</span><span class="sxs-lookup"><span data-stu-id="497cf-128">StrongNameKeyGen Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="497cf-129">StrongNameKeyGenEx 方法</span><span class="sxs-lookup"><span data-stu-id="497cf-129">StrongNameKeyGenEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="497cf-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="497cf-130">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
