---
title: StrongNameKeyInstall 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636705"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="f53da-102">StrongNameKeyInstall 函数</span><span class="sxs-lookup"><span data-stu-id="f53da-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="f53da-103">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="f53da-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="f53da-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="f53da-104">This function has been deprecated.</span></span> <span data-ttu-id="f53da-105">使用[iclrstrongname:: Strongnamekeyinstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="f53da-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="f53da-106">语法</span><span class="sxs-lookup"><span data-stu-id="f53da-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="f53da-107">参数</span><span class="sxs-lookup"><span data-stu-id="f53da-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="f53da-108">[in]密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="f53da-108">[in] The name of the key container.</span></span> <span data-ttu-id="f53da-109">`wszKeyContainer` 必须为非空字符串。</span><span class="sxs-lookup"><span data-stu-id="f53da-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="f53da-110">[in]二进制密钥对。</span><span class="sxs-lookup"><span data-stu-id="f53da-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="f53da-111">[in]大小，以字节为单位的`pbKeyBlob`。</span><span class="sxs-lookup"><span data-stu-id="f53da-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f53da-112">返回值</span><span class="sxs-lookup"><span data-stu-id="f53da-112">Return Value</span></span>

<span data-ttu-id="f53da-113">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f53da-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f53da-114">备注</span><span class="sxs-lookup"><span data-stu-id="f53da-114">Remarks</span></span>

<span data-ttu-id="f53da-115">使用[StrongNameKeyDelete](strongnamekeydelete-function.md)函数来删除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="f53da-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="f53da-116">如果`StrongNameKeyInstall`函数不成功完成，则调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="f53da-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="f53da-117">要求</span><span class="sxs-lookup"><span data-stu-id="f53da-117">Requirements</span></span>

<span data-ttu-id="f53da-118">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f53da-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="f53da-119">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f53da-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="f53da-120">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f53da-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="f53da-121">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f53da-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f53da-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="f53da-122">See also</span></span>

- [<span data-ttu-id="f53da-123">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="f53da-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="f53da-124">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="f53da-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f53da-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f53da-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
