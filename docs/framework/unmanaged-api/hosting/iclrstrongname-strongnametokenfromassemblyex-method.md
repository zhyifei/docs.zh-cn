---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
ms.openlocfilehash: 71fda266c22c4beb1e1f9c81c84d6c56a0a6110e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092574"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="40ec0-102">ICLRStrongName::StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="40ec0-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="40ec0-103">从指定的程序集文件创建强名称令牌，并返回该令牌表示的公钥。</span><span class="sxs-lookup"><span data-stu-id="40ec0-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40ec0-104">语法</span><span class="sxs-lookup"><span data-stu-id="40ec0-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40ec0-105">参数</span><span class="sxs-lookup"><span data-stu-id="40ec0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="40ec0-106">中程序集的可移植可执行（PE）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="40ec0-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="40ec0-107">弄返回的强名称标记。</span><span class="sxs-lookup"><span data-stu-id="40ec0-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="40ec0-108">弄强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="40ec0-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="40ec0-109">弄返回的公钥。</span><span class="sxs-lookup"><span data-stu-id="40ec0-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="40ec0-110">弄公钥的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="40ec0-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="40ec0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="40ec0-111">Return Value</span></span>  
 <span data-ttu-id="40ec0-112">如果方法已成功完成，则 `S_OK`;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="40ec0-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40ec0-113">备注</span><span class="sxs-lookup"><span data-stu-id="40ec0-113">Remarks</span></span>  
 <span data-ttu-id="40ec0-114">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="40ec0-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="40ec0-115">标记是从用于对程序集进行签名的公钥创建的64位哈希。</span><span class="sxs-lookup"><span data-stu-id="40ec0-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="40ec0-116">该令牌是程序集的强名称的一部分，并且可以从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="40ec0-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="40ec0-117">检索到密钥并创建令牌后，应调用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="40ec0-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40ec0-118">要求</span><span class="sxs-lookup"><span data-stu-id="40ec0-118">Requirements</span></span>  
 <span data-ttu-id="40ec0-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="40ec0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40ec0-120">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="40ec0-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="40ec0-121">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="40ec0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40ec0-122">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40ec0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ec0-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="40ec0-123">See also</span></span>

- [<span data-ttu-id="40ec0-124">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="40ec0-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="40ec0-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="40ec0-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
