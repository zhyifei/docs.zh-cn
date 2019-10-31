---
title: StrongNameTokenFromAssembly 函数
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
ms.openlocfilehash: 6b9eca3f2f0267870866874ea27dc65812795f41
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121134"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="489c7-102">StrongNameTokenFromAssembly 函数</span><span class="sxs-lookup"><span data-stu-id="489c7-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="489c7-103">从指定的程序集文件创建强名称令牌。</span><span class="sxs-lookup"><span data-stu-id="489c7-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="489c7-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="489c7-104">This function has been deprecated.</span></span> <span data-ttu-id="489c7-105">改为使用[ICLRStrongName：： StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="489c7-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="489c7-106">语法</span><span class="sxs-lookup"><span data-stu-id="489c7-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="489c7-107">参数</span><span class="sxs-lookup"><span data-stu-id="489c7-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="489c7-108">中程序集的可移植可执行（PE）文件的路径。</span><span class="sxs-lookup"><span data-stu-id="489c7-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="489c7-109">弄返回的强名称标记。</span><span class="sxs-lookup"><span data-stu-id="489c7-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="489c7-110">弄强名称令牌的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="489c7-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="489c7-111">返回值</span><span class="sxs-lookup"><span data-stu-id="489c7-111">Return Value</span></span>  
 <span data-ttu-id="489c7-112">成功完成后 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="489c7-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="489c7-113">备注</span><span class="sxs-lookup"><span data-stu-id="489c7-113">Remarks</span></span>  
 <span data-ttu-id="489c7-114">强名称标记是公钥的缩写形式。</span><span class="sxs-lookup"><span data-stu-id="489c7-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="489c7-115">标记是从用于对程序集进行签名的公钥创建的64位哈希。</span><span class="sxs-lookup"><span data-stu-id="489c7-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="489c7-116">该令牌是程序集的强名称的一部分，并且可以从程序集元数据中读取。</span><span class="sxs-lookup"><span data-stu-id="489c7-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="489c7-117">创建令牌后，应调用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数以释放已分配的内存。</span><span class="sxs-lookup"><span data-stu-id="489c7-117">After the token is created, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="489c7-118">如果 `StrongNameTokenFromAssembly` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="489c7-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="489c7-119">要求</span><span class="sxs-lookup"><span data-stu-id="489c7-119">Requirements</span></span>  
 <span data-ttu-id="489c7-120">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="489c7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="489c7-121">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="489c7-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="489c7-122">**库：** 作为资源包括在 mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="489c7-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="489c7-123">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="489c7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489c7-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="489c7-124">See also</span></span>

- [<span data-ttu-id="489c7-125">StrongNameTokenFromAssembly 方法</span><span class="sxs-lookup"><span data-stu-id="489c7-125">StrongNameTokenFromAssembly Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="489c7-126">StrongNameTokenFromAssemblyEx 方法</span><span class="sxs-lookup"><span data-stu-id="489c7-126">StrongNameTokenFromAssemblyEx Method</span></span>](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="489c7-127">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="489c7-127">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
