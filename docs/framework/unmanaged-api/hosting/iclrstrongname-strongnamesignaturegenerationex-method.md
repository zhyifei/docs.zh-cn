---
title: ICLRStrongName::StrongNameSignatureGenerationEx 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b411a51a5640a924d3eeae5d52102a842966d3fa
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855501"
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a><span data-ttu-id="d093d-102">ICLRStrongName::StrongNameSignatureGenerationEx 方法</span><span class="sxs-lookup"><span data-stu-id="d093d-102">ICLRStrongName::StrongNameSignatureGenerationEx Method</span></span>
<span data-ttu-id="d093d-103">根据指定的标志，为指定的程序集生成强名称签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-103">Generates a strong name signature for the specified assembly, according to the specified flags.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d093d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d093d-104">Syntax</span></span>  
  
```cpp
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d093d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d093d-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d093d-106">中包含要为其生成强名称签名的程序集清单的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="d093d-106">[in] The path to the file that contains the manifest of the assembly for which the strong name signature will be generated.</span></span>  
  
 `wszKeyContainer`  
 <span data-ttu-id="d093d-107">中包含公钥/私钥对的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="d093d-107">[in] The name of the key container that contains the public/private key pair.</span></span>  
  
 <span data-ttu-id="d093d-108">如果`pbKeyBlob`为 null， `wszKeyContainer`则必须在加密服务提供程序（CSP）中指定有效的容器。</span><span class="sxs-lookup"><span data-stu-id="d093d-108">If `pbKeyBlob` is null, `wszKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d093d-109">在这种情况下，存储在容器中的密钥对用于对文件进行签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-109">In this case, the key pair stored in the container is used to sign the file.</span></span>  
  
 <span data-ttu-id="d093d-110">如果`pbKeyBlob`不为 null，则假定密钥对包含在关键的二进制大型对象（BLOB）中。</span><span class="sxs-lookup"><span data-stu-id="d093d-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d093d-111">中指向公钥/私钥对的指针。</span><span class="sxs-lookup"><span data-stu-id="d093d-111">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d093d-112">此对采用 Win32 `CryptExportKey`函数创建的格式。</span><span class="sxs-lookup"><span data-stu-id="d093d-112">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d093d-113">如果`pbKeyBlob`为 null， `wszKeyContainer`则假定指定的密钥容器包含密钥对。</span><span class="sxs-lookup"><span data-stu-id="d093d-113">If `pbKeyBlob` is null, the key container specified by `wszKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d093d-114">中的`pbKeyBlob`大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d093d-114">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbSignatureBlob`  
 <span data-ttu-id="d093d-115">弄指向公共语言运行时返回签名的位置的指针。</span><span class="sxs-lookup"><span data-stu-id="d093d-115">[out] A pointer to the location to which the common language runtime returns the signature.</span></span> <span data-ttu-id="d093d-116">如果`ppbSignatureBlob`为 null，则运行时将签名存储在`wszFilePath`指定的文件中。</span><span class="sxs-lookup"><span data-stu-id="d093d-116">If `ppbSignatureBlob` is null, the runtime stores the signature in the file specified by `wszFilePath`.</span></span>  
  
 <span data-ttu-id="d093d-117">如果`ppbSignatureBlob`不为 null，则公共语言运行时将分配要在其中返回签名的空间。</span><span class="sxs-lookup"><span data-stu-id="d093d-117">If `ppbSignatureBlob` is not null, the common language runtime allocates space in which to return the signature.</span></span> <span data-ttu-id="d093d-118">调用方必须使用[ICLRStrongName：： StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)方法释放此空间。</span><span class="sxs-lookup"><span data-stu-id="d093d-118">The caller must free this space using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbSignatureBlob`  
 <span data-ttu-id="d093d-119">弄返回签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d093d-119">[out] The size, in bytes, of the returned signature.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d093d-120">中以下一个或多个值：</span><span class="sxs-lookup"><span data-stu-id="d093d-120">[in] One or more of the following values:</span></span>  
  
- <span data-ttu-id="d093d-121">`SN_SIGN_ALL_FILES`（0x00000001）-重新计算链接模块的所有哈希。</span><span class="sxs-lookup"><span data-stu-id="d093d-121">`SN_SIGN_ALL_FILES` (0x00000001) - Recompute all hashes for linked modules.</span></span>  
  
- <span data-ttu-id="d093d-122">`SN_TEST_SIGN`（0x00000002）-对程序集进行测试签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-122">`SN_TEST_SIGN` (0x00000002) - Test-sign the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d093d-123">返回值</span><span class="sxs-lookup"><span data-stu-id="d093d-123">Return Value</span></span>  
 <span data-ttu-id="d093d-124">`S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](https://go.microsoft.com/fwlink/?LinkId=213878)）。</span><span class="sxs-lookup"><span data-stu-id="d093d-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d093d-125">备注</span><span class="sxs-lookup"><span data-stu-id="d093d-125">Remarks</span></span>  
 <span data-ttu-id="d093d-126">指定 null `wszFilePath`以计算签名大小，而不创建签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-126">Specify null for `wszFilePath` to calculate the size of the signature without creating the signature.</span></span>  
  
 <span data-ttu-id="d093d-127">签名可以直接存储在文件中，也可以返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="d093d-127">The signature can be either stored directly in the file, or returned to the caller.</span></span>  
  
 <span data-ttu-id="d093d-128">如果`SN_SIGN_ALL_FILES`已指定，但不包括公钥`pbKeyBlob` （和`wszFilePath`均为 null），则会重新计算链接模块的哈希值，但不会对程序集进行重新签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-128">If `SN_SIGN_ALL_FILES` is specified but a public key is not included (both `pbKeyBlob` and `wszFilePath` are null), hashes for linked modules are recomputed, but the assembly is not re-signed.</span></span>  
  
 <span data-ttu-id="d093d-129">如果`SN_TEST_SIGN`指定了，则不会修改公共语言运行时标头以指示程序集使用强名称进行签名。</span><span class="sxs-lookup"><span data-stu-id="d093d-129">If `SN_TEST_SIGN` is specified, the common language runtime header is not modified to indicate that the assembly is signed with a strong name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d093d-130">要求</span><span class="sxs-lookup"><span data-stu-id="d093d-130">Requirements</span></span>  
 <span data-ttu-id="d093d-131">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d093d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d093d-132">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d093d-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d093d-133">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d093d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d093d-134">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d093d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d093d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d093d-135">See also</span></span>

- [<span data-ttu-id="d093d-136">StrongNameSignatureGeneration 方法</span><span class="sxs-lookup"><span data-stu-id="d093d-136">StrongNameSignatureGeneration Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [<span data-ttu-id="d093d-137">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="d093d-137">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
