---
title: IIdentityAuthority 接口
ms.date: 03/30/2017
api_name:
- IIdentityAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IIdentityAuthority
helpviewer_keywords:
- IIdentityAuthority interface [.NET Framework fusion]
ms.assetid: 6277f914-51a8-49be-bec6-52d6d648527d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7421e0d0e1a1f0e1a5fbe0d0eb7d5a0ab2a48b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796425"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="93b4a-102">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="93b4a-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="93b4a-103">管理代码对象的标识键。</span><span class="sxs-lookup"><span data-stu-id="93b4a-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="93b4a-104">方法</span><span class="sxs-lookup"><span data-stu-id="93b4a-104">Methods</span></span>

|<span data-ttu-id="93b4a-105">方法</span><span class="sxs-lookup"><span data-stu-id="93b4a-105">Method</span></span>|<span data-ttu-id="93b4a-106">描述</span><span class="sxs-lookup"><span data-stu-id="93b4a-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="93b4a-107">获取一个值，该值指示两个指定的[IDefinitionIdentity](idefinitionidentity-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="93b4a-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="93b4a-108">获取一个值，该值指示两个指定的[IReferenceIdentity](ireferenceidentity-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="93b4a-108">Gets a value that indicates whether the two specified [IReferenceIdentity](ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="93b4a-109">获取一个值，该值指示两个指定的字符串定义标识表示形式是否相等。</span><span class="sxs-lookup"><span data-stu-id="93b4a-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="93b4a-110">获取一个值，该值指示两个指定的字符串引用标识表示形式是否相等。</span><span class="sxs-lookup"><span data-stu-id="93b4a-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="93b4a-111">获取一个指针，该指针`IDefinitionIdentity`指向表示当前范围内的代码对象的新实例。</span><span class="sxs-lookup"><span data-stu-id="93b4a-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="93b4a-112">获取一个指针，该指针`IReferenceIdentity`指向表示当前范围内的代码对象的新实例。</span><span class="sxs-lookup"><span data-stu-id="93b4a-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="93b4a-113">获取指定`IDefinitionIdentity`的格式化字符串版本。</span><span class="sxs-lookup"><span data-stu-id="93b4a-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="93b4a-114">使用指定`IDefinitionIdentity`的字符串版本填充指定的宽字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="93b4a-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="93b4a-115">获取一个值，该值指示指定`IDefinitionIdentity`的和`IReferenceIdentity`实例是否引用同一代码对象。</span><span class="sxs-lookup"><span data-stu-id="93b4a-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="93b4a-116">获取一个值，该值指示指定的字符串是否引用同一代码对象。</span><span class="sxs-lookup"><span data-stu-id="93b4a-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="93b4a-117">获取一个指针，该指针指向指定`IDefinitionIdentity`的新创建的字符串键。</span><span class="sxs-lookup"><span data-stu-id="93b4a-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="93b4a-118">获取一个指针，该指针指向指定`IReferenceIdentity`的新创建的字符串键。</span><span class="sxs-lookup"><span data-stu-id="93b4a-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="93b4a-119">获取指定`IDefinitionIdentity`的的哈希值。</span><span class="sxs-lookup"><span data-stu-id="93b4a-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="93b4a-120">获取指定`IReferenceIdentity`的的哈希值。</span><span class="sxs-lookup"><span data-stu-id="93b4a-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="93b4a-121">获取指定`IReferenceIdentity`的格式化字符串版本。</span><span class="sxs-lookup"><span data-stu-id="93b4a-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="93b4a-122">使用指定`IReferenceIdentity`的字符串版本填充指定的宽字符缓冲区。</span><span class="sxs-lookup"><span data-stu-id="93b4a-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="93b4a-123">获取一个接口指针，该`IDefinitionIdentity`指针指向从指定的格式化字符串生成的实例。</span><span class="sxs-lookup"><span data-stu-id="93b4a-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="93b4a-124">获取一个接口指针，该`IReferenceIdentity`指针指向从指定的格式化字符串生成的实例。</span><span class="sxs-lookup"><span data-stu-id="93b4a-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="93b4a-125">要求</span><span class="sxs-lookup"><span data-stu-id="93b4a-125">Requirements</span></span>

<span data-ttu-id="93b4a-126">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="93b4a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="93b4a-127">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="93b4a-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="93b4a-128">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93b4a-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="93b4a-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="93b4a-129">See also</span></span>

- [<span data-ttu-id="93b4a-130">合成接口</span><span class="sxs-lookup"><span data-stu-id="93b4a-130">Fusion Interfaces</span></span>](fusion-interfaces.md)
