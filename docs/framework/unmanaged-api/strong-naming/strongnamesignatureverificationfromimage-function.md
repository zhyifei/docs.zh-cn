---
title: StrongNameSignatureVerificationFromImage 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c22339b7d48e89f99d1500cfdda53f00f1234b80
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799080"
---
# <a name="strongnamesignatureverificationfromimage-function"></a><span data-ttu-id="b16d9-102">StrongNameSignatureVerificationFromImage 函数</span><span class="sxs-lookup"><span data-stu-id="b16d9-102">StrongNameSignatureVerificationFromImage Function</span></span>
<span data-ttu-id="b16d9-103">验证已映射到内存的程序集对关联的公钥是否有效。</span><span class="sxs-lookup"><span data-stu-id="b16d9-103">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span>  
  
 <span data-ttu-id="b16d9-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b16d9-104">This function has been deprecated.</span></span> <span data-ttu-id="b16d9-105">改为使用[ICLRStrongName：： StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b16d9-105">Use the [ICLRStrongName::StrongNameVerificationFromImage](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b16d9-106">语法</span><span class="sxs-lookup"><span data-stu-id="b16d9-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b16d9-107">参数</span><span class="sxs-lookup"><span data-stu-id="b16d9-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="b16d9-108">中映射的程序集清单的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="b16d9-108">[in] The relative virtual address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="b16d9-109">中映射的图像的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b16d9-109">[in] The size, in bytes, of the mapped image.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="b16d9-110">中影响验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="b16d9-110">[in] Flags that influence verification behavior.</span></span> <span data-ttu-id="b16d9-111">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b16d9-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="b16d9-112">`SN_INFLAG_FORCE_VER`（0x00000001）-即使需要重写注册表设置，也强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="b16d9-112">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="b16d9-113">`SN_INFLAG_INSTALL`（0x00000002）-指定这是在此映像上执行的第一次验证。</span><span class="sxs-lookup"><span data-stu-id="b16d9-113">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first verification performed on this image.</span></span>  
  
- <span data-ttu-id="b16d9-114">`SN_INFLAG_ADMIN_ACCESS`（0x00000004）-指定缓存只允许具有管理权限的用户访问。</span><span class="sxs-lookup"><span data-stu-id="b16d9-114">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="b16d9-115">`SN_INFLAG_USER_ACCESS`（0x00000008）-指定只有当前用户才能访问程序集。</span><span class="sxs-lookup"><span data-stu-id="b16d9-115">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="b16d9-116">`SN_INFLAG_ALL_ACCESS`（0x00000010）-指定缓存将不提供访问限制。</span><span class="sxs-lookup"><span data-stu-id="b16d9-116">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="b16d9-117">`SN_INFLAG_RUNTIME`（0x80000000）-保留用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="b16d9-117">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="b16d9-118">弄用于附加输出信息的标志。</span><span class="sxs-lookup"><span data-stu-id="b16d9-118">[out] A flag for additional output information.</span></span> <span data-ttu-id="b16d9-119">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="b16d9-119">The following value is supported:</span></span>  
  
- <span data-ttu-id="b16d9-120">`SN_OUTFLAG_WAS_VERIFIED`（0x00000001）-将此值设置为`false` ，以指定验证由于注册表设置而成功。</span><span class="sxs-lookup"><span data-stu-id="b16d9-120">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b16d9-121">返回值</span><span class="sxs-lookup"><span data-stu-id="b16d9-121">Return Value</span></span>  
 <span data-ttu-id="b16d9-122">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="b16d9-122">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b16d9-123">备注</span><span class="sxs-lookup"><span data-stu-id="b16d9-123">Remarks</span></span>  
 <span data-ttu-id="b16d9-124">如果`StrongNameSignatureVerificationFromImage`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="b16d9-124">If the `StrongNameSignatureVerificationFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b16d9-125">要求</span><span class="sxs-lookup"><span data-stu-id="b16d9-125">Requirements</span></span>  
 <span data-ttu-id="b16d9-126">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b16d9-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b16d9-127">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="b16d9-127">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b16d9-128">**类库**作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="b16d9-128">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="b16d9-129">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b16d9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b16d9-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b16d9-130">See also</span></span>

- [<span data-ttu-id="b16d9-131">StrongNameSignatureVerificationFromImage 方法</span><span class="sxs-lookup"><span data-stu-id="b16d9-131">StrongNameSignatureVerificationFromImage Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)
- [<span data-ttu-id="b16d9-132">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="b16d9-132">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
