---
title: ICLRStrongName::GetHashFromFile 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: 798bb0585bfe4cc29afba2fbefae818301704613
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135191"
---
# <a name="iclrstrongnamegethashfromfile-method"></a><span data-ttu-id="025f7-102">ICLRStrongName::GetHashFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="025f7-102">ICLRStrongName::GetHashFromFile Method</span></span>
<span data-ttu-id="025f7-103">生成指定文件内容的哈希。</span><span class="sxs-lookup"><span data-stu-id="025f7-103">Generates a hash over the contents of the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="025f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="025f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="025f7-105">参数</span><span class="sxs-lookup"><span data-stu-id="025f7-105">Parameters</span></span>  
 `szFilePath`  
 <span data-ttu-id="025f7-106">中要进行哈希处理的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="025f7-106">[in] The name of the file to hash.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="025f7-107">[in，out]生成哈希时要使用的算法。</span><span class="sxs-lookup"><span data-stu-id="025f7-107">[in, out] The algorithm to use when generating the hash.</span></span> <span data-ttu-id="025f7-108">有效算法是由 Win32 CryptoAPI 定义的算法。</span><span class="sxs-lookup"><span data-stu-id="025f7-108">Valid algorithms are those defined by the Win32 CryptoAPI.</span></span> <span data-ttu-id="025f7-109">如果 `piHashAlg` 设置为0，则使用默认算法 CALG_SHA-1。</span><span class="sxs-lookup"><span data-stu-id="025f7-109">If `piHashAlg` is set to 0, the default algorithm CALG_SHA-1 is used.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="025f7-110">弄一个字节数组，其中包含生成的哈希。</span><span class="sxs-lookup"><span data-stu-id="025f7-110">[out] A byte array containing the generated hash.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="025f7-111">中`pbHash` 指向的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="025f7-111">[in] The maximum size of the buffer that `pbHash` points to.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="025f7-112">弄返回 `pbHash`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="025f7-112">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="025f7-113">返回值</span><span class="sxs-lookup"><span data-stu-id="025f7-113">Return Value</span></span>  
 <span data-ttu-id="025f7-114">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="025f7-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="025f7-115">备注</span><span class="sxs-lookup"><span data-stu-id="025f7-115">Remarks</span></span>  
 <span data-ttu-id="025f7-116">此方法与[ICLRStrongName：： GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)方法相同，不同之处在于文件名规范为 ANSI 而不是 Unicode。</span><span class="sxs-lookup"><span data-stu-id="025f7-116">This method is the same as the [ICLRStrongName::GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) method, except that the file name specification is ANSI instead of Unicode.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="025f7-117">要求</span><span class="sxs-lookup"><span data-stu-id="025f7-117">Requirements</span></span>  
 <span data-ttu-id="025f7-118">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="025f7-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="025f7-119">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="025f7-119">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="025f7-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="025f7-120">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="025f7-121">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="025f7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="025f7-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="025f7-122">See also</span></span>

- [<span data-ttu-id="025f7-123">GetHashFromFileW 方法</span><span class="sxs-lookup"><span data-stu-id="025f7-123">GetHashFromFileW Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [<span data-ttu-id="025f7-124">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="025f7-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
