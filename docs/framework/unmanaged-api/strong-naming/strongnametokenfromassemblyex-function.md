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
ms.openlocfilehash: c000aad12000a9c76fb6dd805a9b002c021be6ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798839"
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="e3c86-102">StrongNameTokenFromAssemblyEx 函数</span><span class="sxs-lookup"><span data-stu-id="e3c86-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="e3c86-103">从指定的程序集文件创建强名称令牌，并返回该令牌表示的公钥。</span><span class="sxs-lookup"><span data-stu-id="e3c86-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="e3c86-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="e3c86-104">This function has been deprecated.</span></span> <span data-ttu-id="e3c86-105">改为使用[ICLRStrongName：： StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e3c86-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c86-106">语法</span><span class="sxs-lookup"><span data-stu-id="e3c86-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3c86-107">参数</span><span class="sxs-lookup"><span data-stu-id="e3c86-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="e3c86-108">中程序集的可移植可执行（PE）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="e3c86-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="e3c86-109">弄返回的强名称标记。</span><span class="sxs-lookup"><span data-stu-id="e3c86-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="e3c86-110">弄强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e3c86-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="e3c86-111">弄返回的公钥。</span><span class="sxs-lookup"><span data-stu-id="e3c86-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="e3c86-112">弄公钥的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e3c86-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3c86-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e3c86-113">Return Value</span></span>  
 <span data-ttu-id="e3c86-114">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="e3c86-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3c86-115">备注</span><span class="sxs-lookup"><span data-stu-id="e3c86-115">Remarks</span></span>  
 <span data-ttu-id="e3c86-116">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="e3c86-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="e3c86-117">标记是从用于对程序集进行签名的公钥创建的64位哈希。</span><span class="sxs-lookup"><span data-stu-id="e3c86-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="e3c86-118">该令牌是程序集的强名称的一部分，并且可以从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="e3c86-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="e3c86-119">检索到密钥并创建令牌后，应调用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="e3c86-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="e3c86-120">如果`StrongNameTokenFromAssemblyEx`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="e3c86-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c86-121">要求</span><span class="sxs-lookup"><span data-stu-id="e3c86-121">Requirements</span></span>  
 <span data-ttu-id="e3c86-122">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3c86-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c86-123">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="e3c86-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e3c86-124">**类库**作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e3c86-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="e3c86-125">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c86-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c86-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3c86-126">See also</span></span>

- [<span data-ttu-id="e3c86-127">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="e3c86-127">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="e3c86-128">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="e3c86-128">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="e3c86-129">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="e3c86-129">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
