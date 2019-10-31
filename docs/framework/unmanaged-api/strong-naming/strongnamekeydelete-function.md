---
title: StrongNameKeyDelete 函数
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141597"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="c7ce2-102">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="c7ce2-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="c7ce2-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-103">Deletes the specified key container.</span></span>

<span data-ttu-id="c7ce2-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-104">This function has been deprecated.</span></span> <span data-ttu-id="c7ce2-105">改为使用[ICLRStrongName：： StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c7ce2-106">语法</span><span class="sxs-lookup"><span data-stu-id="c7ce2-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="c7ce2-107">参数</span><span class="sxs-lookup"><span data-stu-id="c7ce2-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="c7ce2-108">中要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="c7ce2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c7ce2-109">Return Value</span></span>

<span data-ttu-id="c7ce2-110">成功完成后 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c7ce2-111">备注</span><span class="sxs-lookup"><span data-stu-id="c7ce2-111">Remarks</span></span>

<span data-ttu-id="c7ce2-112">使用[StrongNameKeyInstall](strongnamekeyinstall-function.md)函数将公钥/私钥对导入到容器中。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="c7ce2-113">如果 `StrongNameKeyDelete` 函数未成功完成，请调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数以检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="c7ce2-114">要求</span><span class="sxs-lookup"><span data-stu-id="c7ce2-114">Requirements</span></span>

<span data-ttu-id="c7ce2-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ce2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c7ce2-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="c7ce2-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="c7ce2-117">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c7ce2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="c7ce2-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ce2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ce2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7ce2-119">See also</span></span>

- [<span data-ttu-id="c7ce2-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="c7ce2-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="c7ce2-121">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="c7ce2-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c7ce2-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="c7ce2-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
