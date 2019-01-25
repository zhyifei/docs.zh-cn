---
title: StrongNameHashSize 函数
ms.date: 03/30/2017
api_name:
- StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameHashSize
helpviewer_keywords:
- StrongNameHashSize function [.NET Framework strong naming]
ms.assetid: 738c98d7-a60c-45fe-a296-220af05e6991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ed8b6f047f26235e984fb514381a9b1d85543ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675127"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="45fd3-102">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="45fd3-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="45fd3-103">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="45fd3-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="45fd3-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="45fd3-104">This function has been deprecated.</span></span> <span data-ttu-id="45fd3-105">使用[iclrstrongname:: Strongnamehashsize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="45fd3-105">Use the [ICLRStrongName::StrongNameHashSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45fd3-106">语法</span><span class="sxs-lookup"><span data-stu-id="45fd3-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="45fd3-107">参数</span><span class="sxs-lookup"><span data-stu-id="45fd3-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="45fd3-108">[in]用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="45fd3-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="45fd3-109">[out]返回的缓冲区大小，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="45fd3-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45fd3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="45fd3-110">Return Value</span></span>  
 <span data-ttu-id="45fd3-111">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="45fd3-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="45fd3-112">备注</span><span class="sxs-lookup"><span data-stu-id="45fd3-112">Remarks</span></span>  
 <span data-ttu-id="45fd3-113">如果`StrongNameHashSize`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="45fd3-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45fd3-114">要求</span><span class="sxs-lookup"><span data-stu-id="45fd3-114">Requirements</span></span>  
 <span data-ttu-id="45fd3-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45fd3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45fd3-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="45fd3-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="45fd3-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="45fd3-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45fd3-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45fd3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45fd3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="45fd3-119">See also</span></span>
- [<span data-ttu-id="45fd3-120">StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="45fd3-120">StrongNameHashSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="45fd3-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="45fd3-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
