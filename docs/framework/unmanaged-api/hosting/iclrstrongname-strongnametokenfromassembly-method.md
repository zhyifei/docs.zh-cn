---
title: "ICLRStrongName::StrongNameTokenFromAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameTokenFromAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b236fe3b041277401c2983cf229981253c01328
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="9d681-102">ICLRStrongName::StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="9d681-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="9d681-103">从指定的程序集文件中创建强名称标记。</span><span class="sxs-lookup"><span data-stu-id="9d681-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d681-104">语法</span><span class="sxs-lookup"><span data-stu-id="9d681-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d681-105">参数</span><span class="sxs-lookup"><span data-stu-id="9d681-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="9d681-106">[in]程序集可移植可执行 (PE) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9d681-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="9d681-107">[out]返回强名称标记。</span><span class="sxs-lookup"><span data-stu-id="9d681-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="9d681-108">[out]以字节为单位，强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="9d681-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d681-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9d681-109">Return Value</span></span>  
 <span data-ttu-id="9d681-110">`S_OK`如果成功，则完成的方法否则为该值指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](http://go.microsoft.com/fwlink/?LinkId=213878)有关的列表)。</span><span class="sxs-lookup"><span data-stu-id="9d681-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d681-111">备注</span><span class="sxs-lookup"><span data-stu-id="9d681-111">Remarks</span></span>  
 <span data-ttu-id="9d681-112">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="9d681-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="9d681-113">令牌是从用于对程序集进行签名的公钥创建一个 64 位哈希。</span><span class="sxs-lookup"><span data-stu-id="9d681-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="9d681-114">该令牌属于的强名称的程序集，且可从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="9d681-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="9d681-115">创建令牌后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="9d681-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d681-116">要求</span><span class="sxs-lookup"><span data-stu-id="9d681-116">Requirements</span></span>  
 <span data-ttu-id="9d681-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d681-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d681-118">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9d681-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9d681-119">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="9d681-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d681-120">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d681-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d681-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d681-121">See Also</span></span>  
 [<span data-ttu-id="9d681-122">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="9d681-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="9d681-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="9d681-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
