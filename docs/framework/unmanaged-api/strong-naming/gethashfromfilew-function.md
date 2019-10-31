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
ms.openlocfilehash: db6f39119d143d27c0d3a80a9c65565d4dfd0d39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140672"
---
# <a name="gethashfromfilew-function"></a><span data-ttu-id="46866-102">GetHashFromFileW 函数</span><span class="sxs-lookup"><span data-stu-id="46866-102">GetHashFromFileW Function</span></span>
<span data-ttu-id="46866-103">生成由 Unicode 字符串指定的文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="46866-103">Generates a hash over the contents of the file specified by a Unicode string.</span></span>  
  
 <span data-ttu-id="46866-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="46866-104">This function has been deprecated.</span></span> <span data-ttu-id="46866-105">改为使用[ICLRStrongName：： GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="46866-105">Use the [ICLRStrongName::GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46866-106">语法</span><span class="sxs-lookup"><span data-stu-id="46866-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="46866-107">参数</span><span class="sxs-lookup"><span data-stu-id="46866-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="46866-108">中要进行哈希处理的文件的 Unicode 名称。</span><span class="sxs-lookup"><span data-stu-id="46866-108">[in] The Unicode name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="46866-109">[in，out]生成哈希时要使用的算法。</span><span class="sxs-lookup"><span data-stu-id="46866-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="46866-110">有效算法是由 Win32 CryptoAPI 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="46866-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="46866-111">如果 `piHashAlg` 设置为0，则使用默认算法 CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="46866-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="46866-112">弄一个字节数组，其中包含生成的哈希。</span><span class="sxs-lookup"><span data-stu-id="46866-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="46866-113">中`pbHash`所指向的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="46866-113">[in] The maximum size of the buffer pointed to by `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="46866-114">弄`pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="46866-114">[out] The size, in bytes, of `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46866-115">备注</span><span class="sxs-lookup"><span data-stu-id="46866-115">Remarks</span></span>  
 <span data-ttu-id="46866-116">此函数与[GetHashFromFile](gethashfromfile-function.md)相同，不同之处在于文件名规范是 Unicode 而不是 ANSI。</span><span class="sxs-lookup"><span data-stu-id="46866-116">This function is the same as [GetHashFromFile](gethashfromfile-function.md), except that the file name specification is Unicode instead of ANSI.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46866-117">要求</span><span class="sxs-lookup"><span data-stu-id="46866-117">Requirements</span></span>  
 <span data-ttu-id="46866-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46866-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46866-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="46866-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="46866-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="46866-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46866-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46866-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46866-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="46866-122">See also</span></span>

- [<span data-ttu-id="46866-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="46866-123">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="46866-124">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="46866-124">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="46866-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="46866-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
