---
title: StrongNameTokenFromAssemblyEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20bafd0dfc455538292e47ca33508c251ad68614
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458170"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="6b596-102">StrongNameTokenFromAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="6b596-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="6b596-103">从指定的程序集文件中，创建强名称标记并返回标记表示的公钥。</span><span class="sxs-lookup"><span data-stu-id="6b596-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="6b596-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="6b596-104">This function has been deprecated.</span></span> <span data-ttu-id="6b596-105">使用[iclrstrongname:: Strongnametokenfromassemblyex](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="6b596-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b596-106">语法</span><span class="sxs-lookup"><span data-stu-id="6b596-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b596-107">参数</span><span class="sxs-lookup"><span data-stu-id="6b596-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="6b596-108">[in]程序集可移植可执行 (PE) 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="6b596-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="6b596-109">[out]返回强名称标记。</span><span class="sxs-lookup"><span data-stu-id="6b596-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="6b596-110">[out]以字节为单位，强名称标记的大小。</span><span class="sxs-lookup"><span data-stu-id="6b596-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="6b596-111">[out]返回的公钥。</span><span class="sxs-lookup"><span data-stu-id="6b596-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="6b596-112">[out]以字节为单位的公钥大小。</span><span class="sxs-lookup"><span data-stu-id="6b596-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b596-113">返回值</span><span class="sxs-lookup"><span data-stu-id="6b596-113">Return Value</span></span>  
 <span data-ttu-id="6b596-114">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="6b596-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b596-115">备注</span><span class="sxs-lookup"><span data-stu-id="6b596-115">Remarks</span></span>  
 <span data-ttu-id="6b596-116">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="6b596-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="6b596-117">令牌是从用于对程序集进行签名的公钥创建一个 64 位哈希。</span><span class="sxs-lookup"><span data-stu-id="6b596-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="6b596-118">该令牌属于的强名称的程序集，且可从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="6b596-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="6b596-119">检索到密钥，并创建令牌后，应调用[StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)函数释放分配的内存。</span><span class="sxs-lookup"><span data-stu-id="6b596-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="6b596-120">如果`StrongNameTokenFromAssemblyEx`函数未成功完成，请调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数可检索的最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="6b596-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b596-121">要求</span><span class="sxs-lookup"><span data-stu-id="6b596-121">Requirements</span></span>  
 <span data-ttu-id="6b596-122">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b596-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b596-123">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="6b596-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="6b596-124">**库：** 作为 mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6b596-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="6b596-125">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b596-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b596-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b596-126">See Also</span></span>  
 [<span data-ttu-id="6b596-127">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="6b596-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="6b596-128">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="6b596-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="6b596-129">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6b596-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
