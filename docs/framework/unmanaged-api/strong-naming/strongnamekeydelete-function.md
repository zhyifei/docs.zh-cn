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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799017"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="f7671-102">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="f7671-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="f7671-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="f7671-103">Deletes the specified key container.</span></span>

<span data-ttu-id="f7671-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="f7671-104">This function has been deprecated.</span></span> <span data-ttu-id="f7671-105">改为使用[ICLRStrongName：： StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="f7671-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="f7671-106">语法</span><span class="sxs-lookup"><span data-stu-id="f7671-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="f7671-107">参数</span><span class="sxs-lookup"><span data-stu-id="f7671-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="f7671-108">中要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="f7671-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="f7671-109">返回值</span><span class="sxs-lookup"><span data-stu-id="f7671-109">Return Value</span></span>

<span data-ttu-id="f7671-110">`true`成功完成时;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="f7671-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7671-111">备注</span><span class="sxs-lookup"><span data-stu-id="f7671-111">Remarks</span></span>

<span data-ttu-id="f7671-112">使用[StrongNameKeyInstall](strongnamekeyinstall-function.md)函数将公钥/私钥对导入到容器中。</span><span class="sxs-lookup"><span data-stu-id="f7671-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="f7671-113">如果 `StrongNameKeyDelete` 函数未成功完成，请调用 [StrongNameErrorInfo](strongnameerrorinfo-function.md) 函数来检索上次生成的错误。</span><span class="sxs-lookup"><span data-stu-id="f7671-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="f7671-114">要求</span><span class="sxs-lookup"><span data-stu-id="f7671-114">Requirements</span></span>

<span data-ttu-id="f7671-115">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7671-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f7671-116">**标头：** Stackexchange.redis.strongname</span><span class="sxs-lookup"><span data-stu-id="f7671-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="f7671-117">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="f7671-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="f7671-118">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7671-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f7671-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7671-119">See also</span></span>

- [<span data-ttu-id="f7671-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="f7671-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f7671-121">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="f7671-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="f7671-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="f7671-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
