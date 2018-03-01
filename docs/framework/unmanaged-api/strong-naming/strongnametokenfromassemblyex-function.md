---
title: "StrongNameTokenFromAssemblyEx 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5c118455932fd6c0bf44a486effa90632745d0e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="096e5-102">StrongNameTokenFromAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="096e5-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="096e5-103">从指定的程序集文件中，创建强名称标记并返回标记表示的公钥。</span><span class="sxs-lookup"><span data-stu-id="096e5-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="096e5-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="096e5-104">This function has been deprecated.</span></span> <span data-ttu-id="096e5-105">使用[iclrstrongname:: Strongnametokenfromassemblyex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="096e5-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096e5-106">语法</span><span class="sxs-lookup"><span data-stu-id="096e5-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="096e5-107">参数</span><span class="sxs-lookup"><span data-stu-id="096e5-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="096e5-108">[in]程序集可移植可执行 (PE) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="096e5-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="096e5-109">[out]返回强名称标记。</span><span class="sxs-lookup"><span data-stu-id="096e5-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="096e5-110">[out]以字节为单位，强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="096e5-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="096e5-111">[out]返回的公钥。</span><span class="sxs-lookup"><span data-stu-id="096e5-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="096e5-112">[out]以字节为单位的公钥大小。</span><span class="sxs-lookup"><span data-stu-id="096e5-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="096e5-113">返回值</span><span class="sxs-lookup"><span data-stu-id="096e5-113">Return Value</span></span>  
 <span data-ttu-id="096e5-114">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="096e5-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="096e5-115">备注</span><span class="sxs-lookup"><span data-stu-id="096e5-115">Remarks</span></span>  
 <span data-ttu-id="096e5-116">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="096e5-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="096e5-117">令牌是从用于对程序集进行签名的公钥创建一个 64 位哈希。</span><span class="sxs-lookup"><span data-stu-id="096e5-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="096e5-118">该令牌属于的强名称的程序集，且可从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="096e5-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="096e5-119">检索到密钥，并创建令牌后，应调用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="096e5-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="096e5-120">如果`StrongNameTokenFromAssemblyEx`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="096e5-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="096e5-121">惠?</span><span class="sxs-lookup"><span data-stu-id="096e5-121">Requirements</span></span>  
 <span data-ttu-id="096e5-122">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="096e5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="096e5-123">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="096e5-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="096e5-124">**库：**作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="096e5-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="096e5-125">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="096e5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096e5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="096e5-126">See Also</span></span>  
 [<span data-ttu-id="096e5-127">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="096e5-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="096e5-128">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="096e5-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="096e5-129">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="096e5-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
