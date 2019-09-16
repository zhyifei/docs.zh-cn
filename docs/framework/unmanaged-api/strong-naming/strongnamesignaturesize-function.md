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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798953"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="06630-102">StrongNameSignatureSize 函数</span><span class="sxs-lookup"><span data-stu-id="06630-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="06630-103">返回强名称签名的大小。</span><span class="sxs-lookup"><span data-stu-id="06630-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="06630-104">`StrongNameSignatureSize`通常由编译器用来确定在创建延迟签名程序集时要在文件中保留多少空间。</span><span class="sxs-lookup"><span data-stu-id="06630-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="06630-105">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="06630-105">This function has been deprecated.</span></span> <span data-ttu-id="06630-106">改为使用[ICLRStrongName：： StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="06630-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06630-107">语法</span><span class="sxs-lookup"><span data-stu-id="06630-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="06630-108">参数</span><span class="sxs-lookup"><span data-stu-id="06630-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="06630-109">中[PublicKeyBlob](publickeyblob-structure.md)类型的结构，它包含用于生成强名称签名的密钥对的公共部分。</span><span class="sxs-lookup"><span data-stu-id="06630-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="06630-110">中的`pbPublicKeyBlob`大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="06630-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="06630-111">中存储强名称签名所需的字节数。</span><span class="sxs-lookup"><span data-stu-id="06630-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06630-112">返回值</span><span class="sxs-lookup"><span data-stu-id="06630-112">Return Value</span></span>  
 <span data-ttu-id="06630-113">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="06630-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06630-114">备注</span><span class="sxs-lookup"><span data-stu-id="06630-114">Remarks</span></span>  
 <span data-ttu-id="06630-115">如果`StrongNameSignatureSize`函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="06630-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06630-116">要求</span><span class="sxs-lookup"><span data-stu-id="06630-116">Requirements</span></span>  
 <span data-ttu-id="06630-117">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="06630-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06630-118">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="06630-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="06630-119">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="06630-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06630-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06630-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06630-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="06630-121">See also</span></span>

- [<span data-ttu-id="06630-122">StrongNameSignatureSize 方法</span><span class="sxs-lookup"><span data-stu-id="06630-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="06630-123">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="06630-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
