---
title: StrongNameSignatureSize 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176885"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="31df8-102">StrongNameSignatureSize 函数</span><span class="sxs-lookup"><span data-stu-id="31df8-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="31df8-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="31df8-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="31df8-104">`StrongNameSignatureSize`编译器通常用于确定在创建延迟签名程序集时文件中保留的空间。</span><span class="sxs-lookup"><span data-stu-id="31df8-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="31df8-105">此函数已被弃用。</span><span class="sxs-lookup"><span data-stu-id="31df8-105">This function has been deprecated.</span></span> <span data-ttu-id="31df8-106">改用[ICLR 强名称：：强名称签名大小](../hosting/iclrstrongname-strongnamesignaturesize-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="31df8-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31df8-107">语法</span><span class="sxs-lookup"><span data-stu-id="31df8-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="31df8-108">parameters</span><span class="sxs-lookup"><span data-stu-id="31df8-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="31df8-109">[在][公共密钥Blob](publickeyblob-structure.md)类型的结构，其中包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="31df8-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="31df8-110">[在]的大小（以字节为单位）的大小`pbPublicKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="31df8-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="31df8-111">[在]存储强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="31df8-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31df8-112">返回值</span><span class="sxs-lookup"><span data-stu-id="31df8-112">Return Value</span></span>  
 <span data-ttu-id="31df8-113">`true`成功完成;否则， `false`.</span><span class="sxs-lookup"><span data-stu-id="31df8-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31df8-114">备注</span><span class="sxs-lookup"><span data-stu-id="31df8-114">Remarks</span></span>  
 <span data-ttu-id="31df8-115">如果`StrongNameSignatureSize`函数未成功完成，请调用[StrongNameErrorInfo 函数](strongnameerrorinfo-function.md)以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="31df8-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31df8-116">要求</span><span class="sxs-lookup"><span data-stu-id="31df8-116">Requirements</span></span>  
 <span data-ttu-id="31df8-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="31df8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31df8-118">**标题：** 强名称.h</span><span class="sxs-lookup"><span data-stu-id="31df8-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="31df8-119">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="31df8-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31df8-120">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31df8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31df8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31df8-121">See also</span></span>

- [<span data-ttu-id="31df8-122">StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="31df8-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="31df8-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="31df8-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
