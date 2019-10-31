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
ms.openlocfilehash: c656f73748faf8be7124be65f3ed455f2d5fd07a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105193"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="7215b-102">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="7215b-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="7215b-103">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="7215b-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="7215b-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="7215b-104">This function has been deprecated.</span></span> <span data-ttu-id="7215b-105">改为使用[ICLRStrongName：： StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7215b-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7215b-106">语法</span><span class="sxs-lookup"><span data-stu-id="7215b-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7215b-107">参数</span><span class="sxs-lookup"><span data-stu-id="7215b-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="7215b-108">中用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="7215b-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="7215b-109">弄返回的缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7215b-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7215b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7215b-110">Return Value</span></span>  
 <span data-ttu-id="7215b-111">成功完成后 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="7215b-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7215b-112">备注</span><span class="sxs-lookup"><span data-stu-id="7215b-112">Remarks</span></span>  
 <span data-ttu-id="7215b-113">如果 `StrongNameHashSize` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="7215b-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7215b-114">要求</span><span class="sxs-lookup"><span data-stu-id="7215b-114">Requirements</span></span>  
 <span data-ttu-id="7215b-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7215b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7215b-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="7215b-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7215b-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="7215b-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7215b-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7215b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7215b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="7215b-119">See also</span></span>

- [<span data-ttu-id="7215b-120">StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="7215b-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="7215b-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="7215b-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
