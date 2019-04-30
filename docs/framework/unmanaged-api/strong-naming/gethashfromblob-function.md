---
title: GetHashFromBlob 函数
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000527"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="5d88a-102">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="5d88a-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="5d88a-103">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="5d88a-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="5d88a-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="5d88a-104">This function has been deprecated.</span></span> <span data-ttu-id="5d88a-105">使用[iclrstrongname:: Gethashfromblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="5d88a-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d88a-106">语法</span><span class="sxs-lookup"><span data-stu-id="5d88a-106">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="5d88a-107">参数</span><span class="sxs-lookup"><span data-stu-id="5d88a-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="5d88a-108">[in]指向要进行哈希处理的内存块的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="5d88a-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="5d88a-109">[in]内存块的长度，以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="5d88a-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="5d88a-110">[in、 out]一个常量，它指定哈希算法。</span><span class="sxs-lookup"><span data-stu-id="5d88a-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5d88a-111">使用默认的算法为零。</span><span class="sxs-lookup"><span data-stu-id="5d88a-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="5d88a-112">[out]返回的哈希缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="5d88a-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="5d88a-113">[in]请求的最大大小的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="5d88a-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="5d88a-114">[out]大小 （字节），则返回的`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="5d88a-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="5d88a-115">要求</span><span class="sxs-lookup"><span data-stu-id="5d88a-115">Requirements</span></span>

<span data-ttu-id="5d88a-116">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d88a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="5d88a-117">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="5d88a-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="5d88a-118">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5d88a-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="5d88a-119">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d88a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5d88a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d88a-120">See also</span></span>

- [<span data-ttu-id="5d88a-121">GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="5d88a-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="5d88a-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="5d88a-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)