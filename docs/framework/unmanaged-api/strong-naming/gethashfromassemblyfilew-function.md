---
title: GetHashFromAssemblyFileW 函数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4b748370ff1aff042923002ad827a0e39d99963
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799268"
---
# <a name="gethashfromassemblyfilew-function"></a><span data-ttu-id="cf69b-102">GetHashFromAssemblyFileW 函数</span><span class="sxs-lookup"><span data-stu-id="cf69b-102">GetHashFromAssemblyFileW Function</span></span>
<span data-ttu-id="cf69b-103">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="cf69b-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="cf69b-104">必须将程序集文件的路径指定为 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="cf69b-104">The path to the assembly file must be specified as a Unicode string.</span></span>  
  
 <span data-ttu-id="cf69b-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="cf69b-105">This function has been deprecated.</span></span> <span data-ttu-id="cf69b-106">改为使用[ICLRStrongName：： GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="cf69b-106">Use the [ICLRStrongName::GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf69b-107">语法</span><span class="sxs-lookup"><span data-stu-id="cf69b-107">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf69b-108">参数</span><span class="sxs-lookup"><span data-stu-id="cf69b-108">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="cf69b-109">中要进行哈希处理的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="cf69b-109">[in] The path to the file to be hashed.</span></span> <span data-ttu-id="cf69b-110">此参数必须是 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="cf69b-110">This parameter must be a Unicode string.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="cf69b-111">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="cf69b-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="cf69b-112">使用零作为默认哈希算法。</span><span class="sxs-lookup"><span data-stu-id="cf69b-112">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="cf69b-113">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="cf69b-113">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="cf69b-114">中请求的最大大小`pbHash`。</span><span class="sxs-lookup"><span data-stu-id="cf69b-114">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="cf69b-115">弄返回的的大小（以字节为`pbHash`单位）。</span><span class="sxs-lookup"><span data-stu-id="cf69b-115">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf69b-116">要求</span><span class="sxs-lookup"><span data-stu-id="cf69b-116">Requirements</span></span>  
 <span data-ttu-id="cf69b-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cf69b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf69b-118">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="cf69b-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="cf69b-119">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="cf69b-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf69b-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf69b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf69b-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf69b-121">See also</span></span>

- [<span data-ttu-id="cf69b-122">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="cf69b-122">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="cf69b-123">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="cf69b-123">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="cf69b-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="cf69b-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
