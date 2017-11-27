---
title: "GetHashFromAssemblyFile 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromAssemblyFile
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromAssemblyFile
helpviewer_keywords: GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1598e4e332525f87392ae5b0ad486a735e760651
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="d63e2-102">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="d63e2-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="d63e2-103">获取使用指定的哈希算法对指定的程序集文件的哈希值。</span><span class="sxs-lookup"><span data-stu-id="d63e2-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="d63e2-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="d63e2-104">This function has been deprecated.</span></span> <span data-ttu-id="d63e2-105">使用[iclrstrongname:: Gethashfromassemblyfile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="d63e2-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d63e2-106">语法</span><span class="sxs-lookup"><span data-stu-id="d63e2-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d63e2-107">参数</span><span class="sxs-lookup"><span data-stu-id="d63e2-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="d63e2-108">[in]要进行哈希处理的文件路径。</span><span class="sxs-lookup"><span data-stu-id="d63e2-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="d63e2-109">[在中，out]一个指定的哈希算法的常数。</span><span class="sxs-lookup"><span data-stu-id="d63e2-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d63e2-110">使用默认哈希算法的零。</span><span class="sxs-lookup"><span data-stu-id="d63e2-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="d63e2-111">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="d63e2-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="d63e2-112">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="d63e2-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="d63e2-113">[out]返回的大小，以字节为单位， `pbHash`。</span><span class="sxs-lookup"><span data-stu-id="d63e2-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d63e2-114">要求</span><span class="sxs-lookup"><span data-stu-id="d63e2-114">Requirements</span></span>  
 <span data-ttu-id="d63e2-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d63e2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d63e2-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d63e2-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d63e2-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d63e2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d63e2-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d63e2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63e2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d63e2-119">See Also</span></span>  
 [<span data-ttu-id="d63e2-120">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="d63e2-120">GetHashFromAssemblyFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)  
 [<span data-ttu-id="d63e2-121">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="d63e2-121">GetHashFromAssemblyFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)  
 [<span data-ttu-id="d63e2-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d63e2-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
