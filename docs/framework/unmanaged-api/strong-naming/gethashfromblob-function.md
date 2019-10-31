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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140709"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="c6a4a-102">GetHashFromBlob 函数</span><span class="sxs-lookup"><span data-stu-id="c6a4a-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="c6a4a-103">使用指定的哈希算法获取指定内存地址处的程序集的哈希。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="c6a4a-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-104">This function has been deprecated.</span></span> <span data-ttu-id="c6a4a-105">改为使用[ICLRStrongName：： GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c6a4a-106">语法</span><span class="sxs-lookup"><span data-stu-id="c6a4a-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="c6a4a-107">参数</span><span class="sxs-lookup"><span data-stu-id="c6a4a-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="c6a4a-108">中一个指针，指向要进行哈希处理的内存块的地址。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="c6a4a-109">中内存块的长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="c6a4a-110">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="c6a4a-111">对于默认算法，使用零。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="c6a4a-112">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="c6a4a-113">中请求的最大 `pbHash`大小。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="c6a4a-114">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="c6a4a-115">要求</span><span class="sxs-lookup"><span data-stu-id="c6a4a-115">Requirements</span></span>

<span data-ttu-id="c6a4a-116">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a4a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c6a4a-117">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="c6a4a-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="c6a4a-118">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c6a4a-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="c6a4a-119">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6a4a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c6a4a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a4a-120">See also</span></span>

- [<span data-ttu-id="c6a4a-121">GetHashFromBlob 方法</span><span class="sxs-lookup"><span data-stu-id="c6a4a-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="c6a4a-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c6a4a-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
