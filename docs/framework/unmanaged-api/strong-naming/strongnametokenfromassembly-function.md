---
title: "StrongNameTokenFromAssembly 函数"
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
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 29414522eb2586b00ba3158d79155675cb468815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="bf886-102">StrongNameTokenFromAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="bf886-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="bf886-103">从指定的程序集文件中创建强名称标记。</span><span class="sxs-lookup"><span data-stu-id="bf886-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="bf886-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="bf886-104">This function has been deprecated.</span></span> <span data-ttu-id="bf886-105">使用[iclrstrongname:: Strongnametokenfromassembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="bf886-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf886-106">语法</span><span class="sxs-lookup"><span data-stu-id="bf886-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bf886-107">参数</span><span class="sxs-lookup"><span data-stu-id="bf886-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="bf886-108">[in]程序集可移植可执行 (PE) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bf886-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="bf886-109">[out]返回强名称标记。</span><span class="sxs-lookup"><span data-stu-id="bf886-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="bf886-110">[out]以字节为单位，强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="bf886-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf886-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bf886-111">Return Value</span></span>  
 <span data-ttu-id="bf886-112">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="bf886-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf886-113">备注</span><span class="sxs-lookup"><span data-stu-id="bf886-113">Remarks</span></span>  
 <span data-ttu-id="bf886-114">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="bf886-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="bf886-115">令牌是从用于对程序集进行签名的公钥创建一个 64 位哈希。</span><span class="sxs-lookup"><span data-stu-id="bf886-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="bf886-116">该令牌属于的强名称的程序集，且可从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="bf886-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="bf886-117">创建令牌后，应调用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="bf886-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="bf886-118">如果`StrongNameTokenFromAssembly`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="bf886-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf886-119">惠?</span><span class="sxs-lookup"><span data-stu-id="bf886-119">Requirements</span></span>  
 <span data-ttu-id="bf886-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf886-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf886-121">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="bf886-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="bf886-122">**库：**作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bf886-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="bf886-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf886-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf886-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf886-124">See Also</span></span>  
 [<span data-ttu-id="bf886-125">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="bf886-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="bf886-126">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="bf886-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="bf886-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="bf886-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
