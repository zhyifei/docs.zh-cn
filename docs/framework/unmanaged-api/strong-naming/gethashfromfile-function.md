---
title: GetHashFromFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ffa25b1ec6fda80099f333c1d0a4cf57b76379e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140689"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="1c2e6-102">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="1c2e6-102">GetHashFromFile Function</span></span>
<span data-ttu-id="1c2e6-103">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="1c2e6-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-104">This function has been deprecated.</span></span> <span data-ttu-id="1c2e6-105">改为使用[ICLRStrongName：： GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c2e6-106">语法</span><span class="sxs-lookup"><span data-stu-id="1c2e6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c2e6-107">参数</span><span class="sxs-lookup"><span data-stu-id="1c2e6-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="1c2e6-108">中要进行哈希处理的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="1c2e6-109">[in，out]生成哈希时要使用的算法。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="1c2e6-110">有效算法是由 Win32 CryptoAPI 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="1c2e6-111">如果 `piHashAlg` 设置为0，则使用默认算法 CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="1c2e6-112">弄一个字节数组，其中包含生成的哈希。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="1c2e6-113">中`pbHash` 指向的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="1c2e6-114">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c2e6-115">备注</span><span class="sxs-lookup"><span data-stu-id="1c2e6-115">Remarks</span></span>  
 <span data-ttu-id="1c2e6-116">此函数与[GetHashFromFileW](gethashfromfilew-function.md)相同，不同之处在于文件名规范为 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c2e6-117">要求</span><span class="sxs-lookup"><span data-stu-id="1c2e6-117">Requirements</span></span>  
 <span data-ttu-id="1c2e6-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2e6-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c2e6-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="1c2e6-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1c2e6-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1c2e6-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c2e6-121">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c2e6-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c2e6-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2e6-122">See also</span></span>

- [<span data-ttu-id="1c2e6-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="1c2e6-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="1c2e6-124">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="1c2e6-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="1c2e6-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="1c2e6-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
