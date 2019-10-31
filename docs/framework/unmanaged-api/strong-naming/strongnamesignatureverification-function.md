---
title: StrongNameSignatureVerification 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
ms.openlocfilehash: 7dd61be008ba08ca2b28ae3e7e8ff6326f8a41d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129235"
---
# <a name="strongnamesignatureverification-function"></a><span data-ttu-id="4f78f-102">StrongNameSignatureVerification 函数</span><span class="sxs-lookup"><span data-stu-id="4f78f-102">StrongNameSignatureVerification Function</span></span>
<span data-ttu-id="4f78f-103">获取一个值，该值指示提供的路径中的程序集清单是否包含根据指定标志验证的强名称签名。</span><span class="sxs-lookup"><span data-stu-id="4f78f-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span>  
  
 <span data-ttu-id="4f78f-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="4f78f-104">This function has been deprecated.</span></span> <span data-ttu-id="4f78f-105">改为使用[ICLRStrongName：： StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4f78f-105">Use the [ICLRStrongName::StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f78f-106">语法</span><span class="sxs-lookup"><span data-stu-id="4f78f-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f78f-107">参数</span><span class="sxs-lookup"><span data-stu-id="4f78f-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="4f78f-108">中要验证的程序集的可移植可执行文件（.dll 或 .exe）的路径。</span><span class="sxs-lookup"><span data-stu-id="4f78f-108">[in] The path to the portable executable (.dll or .exe) file for the assembly to verify.</span></span>  
  
 `dwInFlags`  
 <span data-ttu-id="4f78f-109">中用于修改验证行为的标志。</span><span class="sxs-lookup"><span data-stu-id="4f78f-109">[in] Flags to modify the verification behavior.</span></span> <span data-ttu-id="4f78f-110">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="4f78f-110">The following values are supported:</span></span>  
  
- <span data-ttu-id="4f78f-111">`SN_INFLAG_FORCE_VER` （0x00000001）-即使需要重写注册表设置，也强制进行验证。</span><span class="sxs-lookup"><span data-stu-id="4f78f-111">`SN_INFLAG_FORCE_VER` (0x00000001) - Forces verification even if it is necessary to override registry settings.</span></span>  
  
- <span data-ttu-id="4f78f-112">`SN_INFLAG_INSTALL` （0x00000002）-指定这是第一次验证清单。</span><span class="sxs-lookup"><span data-stu-id="4f78f-112">`SN_INFLAG_INSTALL` (0x00000002) - Specifies that this is the first time the manifest is verified.</span></span>  
  
- <span data-ttu-id="4f78f-113">`SN_INFLAG_ADMIN_ACCESS` （0x00000004）-指定缓存只允许具有管理权限的用户访问。</span><span class="sxs-lookup"><span data-stu-id="4f78f-113">`SN_INFLAG_ADMIN_ACCESS` (0x00000004) - Specifies that the cache will allow access only to users who have administrative privileges.</span></span>  
  
- <span data-ttu-id="4f78f-114">`SN_INFLAG_USER_ACCESS` （0x00000008）-指定只有当前用户才能访问该程序集。</span><span class="sxs-lookup"><span data-stu-id="4f78f-114">`SN_INFLAG_USER_ACCESS` (0x00000008) - Specifies that the assembly will be accessible only to the current user.</span></span>  
  
- <span data-ttu-id="4f78f-115">`SN_INFLAG_ALL_ACCESS` （0x00000010）-指定缓存将不提供访问限制。</span><span class="sxs-lookup"><span data-stu-id="4f78f-115">`SN_INFLAG_ALL_ACCESS` (0x00000010) - Specifies that the cache will provide no guarantees of access restriction.</span></span>  
  
- <span data-ttu-id="4f78f-116">`SN_INFLAG_RUNTIME` （0x80000000）-保留用于内部调试。</span><span class="sxs-lookup"><span data-stu-id="4f78f-116">`SN_INFLAG_RUNTIME` (0x80000000) - Reserved for internal debugging.</span></span>  
  
 `pdwOutFlags`  
 <span data-ttu-id="4f78f-117">弄指示强名称签名是否已验证的标志。</span><span class="sxs-lookup"><span data-stu-id="4f78f-117">[out] Flags indicating whether the strong name signature was verified.</span></span> <span data-ttu-id="4f78f-118">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="4f78f-118">The following value is supported:</span></span>  
  
- <span data-ttu-id="4f78f-119">`SN_OUTFLAG_WAS_VERIFIED` （0x00000001）-此值设置为 `false` 以指定验证是否已成功（因为注册表设置）。</span><span class="sxs-lookup"><span data-stu-id="4f78f-119">`SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - This value is set to `false` to specify that the verification succeeded due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f78f-120">返回值</span><span class="sxs-lookup"><span data-stu-id="4f78f-120">Return Value</span></span>  
 <span data-ttu-id="4f78f-121">如果验证成功，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="4f78f-121">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f78f-122">要求</span><span class="sxs-lookup"><span data-stu-id="4f78f-122">Requirements</span></span>  
 <span data-ttu-id="4f78f-123">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f78f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f78f-124">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="4f78f-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4f78f-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="4f78f-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f78f-126">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f78f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f78f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f78f-127">See also</span></span>

- [<span data-ttu-id="4f78f-128">StrongNameSignatureVerification 方法</span><span class="sxs-lookup"><span data-stu-id="4f78f-128">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="4f78f-129">StrongNameSignatureVerificationEx 方法</span><span class="sxs-lookup"><span data-stu-id="4f78f-129">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="4f78f-130">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="4f78f-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
