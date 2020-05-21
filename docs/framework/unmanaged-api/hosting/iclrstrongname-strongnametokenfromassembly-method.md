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
ms.openlocfilehash: e71fcf80b51edc318bbc7d81bb277c614184ee55
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762508"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="e5b85-102">ICLRStrongName::StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="e5b85-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="e5b85-103">从指定的程序集文件创建强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="e5b85-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5b85-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5b85-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5b85-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5b85-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e5b85-106">中程序集的可移植可执行（PE）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="e5b85-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="e5b85-107">弄返回的强名称标记。</span><span class="sxs-lookup"><span data-stu-id="e5b85-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="e5b85-108">弄强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5b85-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e5b85-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e5b85-109">Return Value</span></span>  
 <span data-ttu-id="e5b85-110">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。</span><span class="sxs-lookup"><span data-stu-id="e5b85-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5b85-111">注解</span><span class="sxs-lookup"><span data-stu-id="e5b85-111">Remarks</span></span>  
 <span data-ttu-id="e5b85-112">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="e5b85-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="e5b85-113">标记是从用于对程序集进行签名的公钥创建的64位哈希。</span><span class="sxs-lookup"><span data-stu-id="e5b85-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="e5b85-114">该令牌是程序集的强名称的一部分，并且可以从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="e5b85-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="e5b85-115">创建令牌后，应调用[ICLRStrongName：： StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md)方法来释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e5b85-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5b85-116">要求</span><span class="sxs-lookup"><span data-stu-id="e5b85-116">Requirements</span></span>  
 <span data-ttu-id="e5b85-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5b85-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5b85-118">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="e5b85-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e5b85-119">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e5b85-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5b85-120">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5b85-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5b85-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5b85-121">See also</span></span>

- [<span data-ttu-id="e5b85-122">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="e5b85-122">StrongNameTokenFromAssemblyEx Method</span></span>](iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="e5b85-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e5b85-123">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
