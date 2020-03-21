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
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176976"
---
# <a name="gethashfromfile-function"></a><span data-ttu-id="836e8-102">GetHashFromFile 函数</span><span class="sxs-lookup"><span data-stu-id="836e8-102">GetHashFromFile Function</span></span>
<span data-ttu-id="836e8-103">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="836e8-103">Generates a hash over the contents of the specified file.</span></span>  
  
 <span data-ttu-id="836e8-104">此函数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="836e8-104">This function has been deprecated.</span></span> <span data-ttu-id="836e8-105">改用[ICLR 强名称：：获取哈希文件](../hosting/iclrstrongname-gethashfromfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="836e8-105">Use the [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="836e8-106">语法</span><span class="sxs-lookup"><span data-stu-id="836e8-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="836e8-107">parameters</span><span class="sxs-lookup"><span data-stu-id="836e8-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="836e8-108">[在]要哈希的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="836e8-108">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="836e8-109">[进出]生成哈希时使用的算法。</span><span class="sxs-lookup"><span data-stu-id="836e8-109">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="836e8-110">有效的算法是由 Win32 加密 API 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="836e8-110">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="836e8-111">如果`piHashAlg`设置为 0，则使用默认算法CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="836e8-111">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="836e8-112">[出]包含生成的哈希的字节数组。</span><span class="sxs-lookup"><span data-stu-id="836e8-112">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="836e8-113">[在]`pbHash`指向的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="836e8-113">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="836e8-114">[出]返回`pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="836e8-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="836e8-115">备注</span><span class="sxs-lookup"><span data-stu-id="836e8-115">Remarks</span></span>  
 <span data-ttu-id="836e8-116">此函数与[GetHashFromFileW](gethashfromfilew-function.md)相同，只不过文件名规范是 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="836e8-116">This function is the same as [GetHashFromFileW](gethashfromfilew-function.md), except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="836e8-117">要求</span><span class="sxs-lookup"><span data-stu-id="836e8-117">Requirements</span></span>  
 <span data-ttu-id="836e8-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="836e8-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="836e8-119">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="836e8-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="836e8-120">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="836e8-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="836e8-121">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="836e8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="836e8-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="836e8-122">See also</span></span>

- [<span data-ttu-id="836e8-123">GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="836e8-123">GetHashFromFile Method</span></span>](../hosting/iclrstrongname-gethashfromfile-method.md)
- [<span data-ttu-id="836e8-124">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="836e8-124">GetHashFromFileW Method</span></span>](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="836e8-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="836e8-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
