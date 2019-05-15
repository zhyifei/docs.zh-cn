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
ms.openlocfilehash: 717d2104db8addf40e5187cee4cc8c46e5dc355e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636741"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="ecea3-102">StrongNameKeyDelete 函数</span><span class="sxs-lookup"><span data-stu-id="ecea3-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="ecea3-103">删除指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="ecea3-103">Deletes the specified key container.</span></span>

<span data-ttu-id="ecea3-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="ecea3-104">This function has been deprecated.</span></span> <span data-ttu-id="ecea3-105">使用[iclrstrongname:: Strongnamekeydelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="ecea3-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ecea3-106">语法</span><span class="sxs-lookup"><span data-stu-id="ecea3-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="ecea3-107">参数</span><span class="sxs-lookup"><span data-stu-id="ecea3-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="ecea3-108">[in]若要删除的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="ecea3-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="ecea3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ecea3-109">Return Value</span></span>

<span data-ttu-id="ecea3-110">`true` 在成功完成;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ecea3-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ecea3-111">备注</span><span class="sxs-lookup"><span data-stu-id="ecea3-111">Remarks</span></span>

<span data-ttu-id="ecea3-112">使用[StrongNameKeyInstall](strongnamekeyinstall-function.md)函数导入容器的公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="ecea3-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="ecea3-113">如果`StrongNameKeyDelete`函数不成功完成，则调用[StrongNameErrorInfo](strongnameerrorinfo-function.md)函数检索最后一个生成的错误。</span><span class="sxs-lookup"><span data-stu-id="ecea3-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="ecea3-114">要求</span><span class="sxs-lookup"><span data-stu-id="ecea3-114">Requirements</span></span>

<span data-ttu-id="ecea3-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ecea3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ecea3-116">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ecea3-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="ecea3-117">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ecea3-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ecea3-118">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecea3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ecea3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecea3-119">See also</span></span>

- [<span data-ttu-id="ecea3-120">StrongNameKeyDelete 方法</span><span class="sxs-lookup"><span data-stu-id="ecea3-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="ecea3-121">StrongNameKeyInstall 方法</span><span class="sxs-lookup"><span data-stu-id="ecea3-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="ecea3-122">ICLRStrongName 接口</span><span class="sxs-lookup"><span data-stu-id="ecea3-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
