---
title: GetHashFromAssemblyFile 函数
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFile
helpviewer_keywords:
- GetHashFromAssemblyFile function [.NET Framework strong naming]
ms.assetid: 751ed69f-b7ab-4e07-80de-e17ca9319b0c
topic_type:
- apiref
ms.openlocfilehash: 866b34acae333f043d8e13f4d0ebd55f32046334
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140727"
---
# <a name="gethashfromassemblyfile-function"></a><span data-ttu-id="5d873-102">GetHashFromAssemblyFile 函数</span><span class="sxs-lookup"><span data-stu-id="5d873-102">GetHashFromAssemblyFile Function</span></span>
<span data-ttu-id="5d873-103">使用指定的哈希算法获取指定程序集文件的哈希。</span><span class="sxs-lookup"><span data-stu-id="5d873-103">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="5d873-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="5d873-104">This function has been deprecated.</span></span> <span data-ttu-id="5d873-105">改为使用[ICLRStrongName：： GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5d873-105">Use the [ICLRStrongName::GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d873-106">语法</span><span class="sxs-lookup"><span data-stu-id="5d873-106">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d873-107">参数</span><span class="sxs-lookup"><span data-stu-id="5d873-107">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="5d873-108">中要进行哈希处理的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="5d873-108">[in] The path to the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="5d873-109">[in，out]指定哈希算法的常量。</span><span class="sxs-lookup"><span data-stu-id="5d873-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="5d873-110">使用零作为默认哈希算法。</span><span class="sxs-lookup"><span data-stu-id="5d873-110">Use zero for the default hash algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="5d873-111">弄返回的哈希缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5d873-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="5d873-112">中请求的最大 `pbHash`大小。</span><span class="sxs-lookup"><span data-stu-id="5d873-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="5d873-113">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5d873-113">[out] The returned size, in bytes, of `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d873-114">要求</span><span class="sxs-lookup"><span data-stu-id="5d873-114">Requirements</span></span>  
 <span data-ttu-id="5d873-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d873-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d873-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="5d873-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5d873-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5d873-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d873-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d873-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d873-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d873-119">See also</span></span>

- [<span data-ttu-id="5d873-120">GetHashFromAssemblyFile 方法</span><span class="sxs-lookup"><span data-stu-id="5d873-120">GetHashFromAssemblyFile Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [<span data-ttu-id="5d873-121">GetHashFromAssemblyFileW 方法</span><span class="sxs-lookup"><span data-stu-id="5d873-121">GetHashFromAssemblyFileW Method</span></span>](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [<span data-ttu-id="5d873-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="5d873-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
