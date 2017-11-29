---
title: "StrongNameHashSize 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameHashSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameHashSize
helpviewer_keywords: StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: baf9c9b2219ff3fb784972b1f54a2b50dcd8657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="e92df-102">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="e92df-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="e92df-103">获取使用指定的哈希算法的哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="e92df-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="e92df-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="e92df-104">This function has been deprecated.</span></span> <span data-ttu-id="e92df-105">使用[iclrstrongname:: Strongnamehashsize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="e92df-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e92df-106">语法</span><span class="sxs-lookup"><span data-stu-id="e92df-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e92df-107">参数</span><span class="sxs-lookup"><span data-stu-id="e92df-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e92df-108">[in]用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="e92df-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e92df-109">[out]返回的缓冲区大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="e92df-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e92df-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e92df-110">Return Value</span></span>  
 <span data-ttu-id="e92df-111">`true`在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="e92df-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e92df-112">备注</span><span class="sxs-lookup"><span data-stu-id="e92df-112">Remarks</span></span>  
 <span data-ttu-id="e92df-113">如果`StrongNameHashSize`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="e92df-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e92df-114">要求</span><span class="sxs-lookup"><span data-stu-id="e92df-114">Requirements</span></span>  
 <span data-ttu-id="e92df-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e92df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e92df-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e92df-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e92df-117">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e92df-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e92df-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e92df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e92df-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e92df-119">See Also</span></span>  
 [<span data-ttu-id="e92df-120">StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="e92df-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)  
 [<span data-ttu-id="e92df-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e92df-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
