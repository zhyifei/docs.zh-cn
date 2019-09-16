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
ms.openlocfilehash: 53384a5aa7f8d11f868057f892f7b60aac2e9f02
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799037"
---
# <a name="strongnamehashsize-function"></a><span data-ttu-id="f7459-102">StrongNameHashSize 函数</span><span class="sxs-lookup"><span data-stu-id="f7459-102">StrongNameHashSize Function</span></span>
<span data-ttu-id="f7459-103">使用指定的哈希算法获取哈希所需的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="f7459-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f7459-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="f7459-104">This function has been deprecated.</span></span> <span data-ttu-id="f7459-105">改为使用[ICLRStrongName：： StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f7459-105">Use the [ICLRStrongName::StrongNameHashSize](../hosting/iclrstrongname-strongnamehashsize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7459-106">语法</span><span class="sxs-lookup"><span data-stu-id="f7459-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7459-107">参数</span><span class="sxs-lookup"><span data-stu-id="f7459-107">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="f7459-108">中用于计算缓冲区大小的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="f7459-108">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="f7459-109">弄返回的缓冲区大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f7459-109">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f7459-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f7459-110">Return Value</span></span>  
 <span data-ttu-id="f7459-111">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f7459-111">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7459-112">备注</span><span class="sxs-lookup"><span data-stu-id="f7459-112">Remarks</span></span>  
 <span data-ttu-id="f7459-113">如果`StrongNameHashSize`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="f7459-113">If the `StrongNameHashSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7459-114">要求</span><span class="sxs-lookup"><span data-stu-id="f7459-114">Requirements</span></span>  
 <span data-ttu-id="f7459-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7459-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7459-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="f7459-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f7459-117">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f7459-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7459-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7459-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7459-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7459-119">See also</span></span>

- [<span data-ttu-id="f7459-120">StrongNameHashSize 方法</span><span class="sxs-lookup"><span data-stu-id="f7459-120">StrongNameHashSize Method</span></span>](../hosting/iclrstrongname-strongnamehashsize-method.md)
- [<span data-ttu-id="f7459-121">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f7459-121">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
