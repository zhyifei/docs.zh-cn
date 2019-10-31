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
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125198"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="6862e-102">StrongNameKeyInstall 函数</span><span class="sxs-lookup"><span data-stu-id="6862e-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="6862e-103">将公钥/私钥对导入容器。</span><span class="sxs-lookup"><span data-stu-id="6862e-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="6862e-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="6862e-104">This function has been deprecated.</span></span> <span data-ttu-id="6862e-105">改为使用[ICLRStrongName：： StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6862e-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="6862e-106">语法</span><span class="sxs-lookup"><span data-stu-id="6862e-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="6862e-107">参数</span><span class="sxs-lookup"><span data-stu-id="6862e-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="6862e-108">中密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="6862e-108">[in] The name of the key container.</span></span> <span data-ttu-id="6862e-109">`wszKeyContainer` 必须为非空字符串。</span><span class="sxs-lookup"><span data-stu-id="6862e-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="6862e-110">中二进制密钥对。</span><span class="sxs-lookup"><span data-stu-id="6862e-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="6862e-111">中`pbKeyBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6862e-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6862e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6862e-112">Return Value</span></span>

<span data-ttu-id="6862e-113">成功完成后 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="6862e-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6862e-114">备注</span><span class="sxs-lookup"><span data-stu-id="6862e-114">Remarks</span></span>

<span data-ttu-id="6862e-115">使用[StrongNameKeyDelete](strongnamekeydelete-function.md)函数可删除密钥容器。</span><span class="sxs-lookup"><span data-stu-id="6862e-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="6862e-116">如果 `StrongNameKeyInstall` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="6862e-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="6862e-117">要求</span><span class="sxs-lookup"><span data-stu-id="6862e-117">Requirements</span></span>

<span data-ttu-id="6862e-118">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6862e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="6862e-119">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="6862e-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="6862e-120">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="6862e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="6862e-121">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6862e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6862e-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6862e-122">See also</span></span>

- [<span data-ttu-id="6862e-123">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="6862e-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="6862e-124">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="6862e-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="6862e-125">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="6862e-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
