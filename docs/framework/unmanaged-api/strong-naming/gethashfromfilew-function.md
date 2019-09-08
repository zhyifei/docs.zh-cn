---
title: GetHashFromFileW 函数
ms.date: 03/30/2017
api_name:
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799197"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="5bf9d-102">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="5bf9d-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="5bf9d-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="5bf9d-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-104">This function has been deprecated.</span></span> <span data-ttu-id="5bf9d-105">改为使用[ICLRStrongName：： GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf9d-106">语法</span><span class="sxs-lookup"><span data-stu-id="5bf9d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf9d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5bf9d-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5bf9d-108">中要进行哈希处理的文件的 Unicode 名称。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5bf9d-109">[in，out]生成哈希时要使用的算法。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="5bf9d-110">有效算法是由 Win32 CryptoAPI 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="5bf9d-111">如果`piHashAlg`设置为0，则使用默认算法 CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5bf9d-112">弄一个字节数组，其中包含生成的哈希。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5bf9d-113">中所指向`pbHash`的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5bf9d-114">弄的`pbHash`大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bf9d-115">备注</span><span class="sxs-lookup"><span data-stu-id="5bf9d-115">Remarks</span></span>  
 <span data-ttu-id="5bf9d-116">此函数与[GetHashFromFile](gethashfromfile-function.md)相同，不同之处在于文件名规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf9d-117">要求</span><span class="sxs-lookup"><span data-stu-id="5bf9d-117">Requirements</span></span>  
 <span data-ttu-id="5bf9d-118">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bf9d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf9d-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="5bf9d-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5bf9d-120">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5bf9d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bf9d-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf9d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf9d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bf9d-122">See also</span></span>

- [<span data-ttu-id="5bf9d-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="5bf9d-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="5bf9d-124">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="5bf9d-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="5bf9d-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="5bf9d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
