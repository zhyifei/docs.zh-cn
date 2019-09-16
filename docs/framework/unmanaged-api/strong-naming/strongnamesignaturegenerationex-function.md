---
title: StrongNameSignatureGenerationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGenerationEx
helpviewer_keywords:
- StrongNameSignatureGenerationEx function [.NET Framework strong naming]
ms.assetid: 9a75469e-aa49-4e32-ad48-3bafd5202f09
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 89398c221dcf9d6f89027f15da4062bc7ed67e3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798981"
---
# <a name="strongnamesignaturegenerationex-function"></a><span data-ttu-id="5b628-102">StrongNameSignatureGenerationEx 函数</span><span class="sxs-lookup"><span data-stu-id="5b628-102">StrongNameSignatureGenerationEx Function</span></span>
<span data-ttu-id="5b628-103">根据指定的标志，为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
 <span data-ttu-id="5b628-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="5b628-104">This function has been deprecated.</span></span> <span data-ttu-id="5b628-105">改为使用[ICLRStrongName：： StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5b628-105">Use the [ICLRStrongName::StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b628-106">语法</span><span class="sxs-lookup"><span data-stu-id="5b628-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b628-107">参数</span><span class="sxs-lookup"><span data-stu-id="5b628-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5b628-108">中包含要为其生成强名称签名的程序集清单的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="5b628-108">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="5b628-109">中包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="5b628-109">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="5b628-110">如果`pbKeyBlob`为 null， `wszKeyContainer`则必须在加密服务提供程序（CSP）中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="5b628-110">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="5b628-111">在这种情况下，存储在容器中的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-111">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="5b628-112">如果`pbKeyBlob`不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。</span><span class="sxs-lookup"><span data-stu-id="5b628-112">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5b628-113">中指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="5b628-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="5b628-114">此对采用 Win32 `CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="5b628-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="5b628-115">如果`pbKeyBlob`为 null， `wszKeyContainer`则假定指定的密钥容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="5b628-115">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5b628-116">中的`pbKeyBlob`大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5b628-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="5b628-117">弄指向公共语言运行时返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="5b628-117">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="5b628-118">如果`ppbSignatureBlob`为 null，则运行时将签名存储在`wszFilePath`指定的文件中。</span><span class="sxs-lookup"><span data-stu-id="5b628-118">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="5b628-119">如果`ppbSignatureBlob`不为 null，则公共语言运行时将分配要在其中返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="5b628-119">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="5b628-120">调用方必须使用[StrongNameFreeBuffer](strongnamefreebuffer-function.md)函数释放此空间。</span><span class="sxs-lookup"><span data-stu-id="5b628-120">The caller must free this space using the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="5b628-121">弄返回签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5b628-121">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5b628-122">中以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="5b628-122">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="5b628-123">`SN_SIGN_ALL_FILES`（0x00000001）-重新计算链接模块的所有哈希。</span><span class="sxs-lookup"><span data-stu-id="5b628-123">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="5b628-124">`SN_TEST_SIGN`（0x00000002）-对程序集进行测试签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-124">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b628-125">返回值</span><span class="sxs-lookup"><span data-stu-id="5b628-125">Return Value</span></span>  
 <span data-ttu-id="5b628-126">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="5b628-126">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b628-127">备注</span><span class="sxs-lookup"><span data-stu-id="5b628-127">Remarks</span></span>  
 <span data-ttu-id="5b628-128">指定 null `wszFilePath`以计算签名大小，而不创建签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-128">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="5b628-129">签名可以直接存储在文件中，也可以返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="5b628-129">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="5b628-130">如果`SN_SIGN_ALL_FILES`已指定，但不包括公钥`pbKeyBlob` （和`wszFilePath`均为 null），则会重新计算链接模块的哈希值，但不会对程序集进行重新签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-130">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="5b628-131">如果`SN_TEST_SIGN`指定了，则不会修改公共语言运行时标头以指示程序集使用强名称进行签名。</span><span class="sxs-lookup"><span data-stu-id="5b628-131">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
 <span data-ttu-id="5b628-132">如果 `StrongNameSignatureGenerationEx` 函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="5b628-132">If the `StrongNameSignatureGenerationEx` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b628-133">要求</span><span class="sxs-lookup"><span data-stu-id="5b628-133">Requirements</span></span>  
 <span data-ttu-id="5b628-134">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5b628-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b628-135">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="5b628-135">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5b628-136">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5b628-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b628-137">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b628-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b628-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b628-138">See also</span></span>

- [<span data-ttu-id="5b628-139">StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="5b628-139">StrongNameSignatureGenerationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [<span data-ttu-id="5b628-140">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="5b628-140">StrongNameSignatureGeneration Method</span></span>](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="5b628-141">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="5b628-141">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
