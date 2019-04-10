---
title: ICLRStrongName::StrongNameTokenFromAssembly 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229246"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="88747-102">ICLRStrongName::StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="88747-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="88747-103">从指定的程序集文件创建强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="88747-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88747-104">语法</span><span class="sxs-lookup"><span data-stu-id="88747-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88747-105">参数</span><span class="sxs-lookup"><span data-stu-id="88747-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="88747-106">[in]程序集可移植可执行 (PE) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="88747-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="88747-107">[out]返回的强名称标记中。</span><span class="sxs-lookup"><span data-stu-id="88747-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="88747-108">[out]以字节为单位的强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="88747-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="88747-109">返回值</span><span class="sxs-lookup"><span data-stu-id="88747-109">Return Value</span></span>  
 `S_OK` <span data-ttu-id="88747-110">如果成功，则完成的方法否则为指示失败的 HRESULT 值 (请参阅[常见的 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)列表)。</span><span class="sxs-lookup"><span data-stu-id="88747-110">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88747-111">备注</span><span class="sxs-lookup"><span data-stu-id="88747-111">Remarks</span></span>  
 <span data-ttu-id="88747-112">强名称标记是简写形式的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="88747-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="88747-113">令牌是通过使用程序集进行签名的公钥创建一个 64 位哈希。</span><span class="sxs-lookup"><span data-stu-id="88747-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="88747-114">该令牌是程序集的强名称的一部分，且可以从程序集元数据读取。</span><span class="sxs-lookup"><span data-stu-id="88747-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="88747-115">创建令牌后，应调用[iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法，以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="88747-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88747-116">要求</span><span class="sxs-lookup"><span data-stu-id="88747-116">Requirements</span></span>  
 <span data-ttu-id="88747-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88747-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88747-118">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="88747-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="88747-119">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="88747-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="88747-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="88747-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88747-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="88747-121">See also</span></span>

- [<span data-ttu-id="88747-122">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="88747-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="88747-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="88747-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
