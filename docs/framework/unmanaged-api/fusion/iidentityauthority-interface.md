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
ms.openlocfilehash: 263dc0f9d686440aaa23e359c26db1b4d3d09b1e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375958"
---
# <a name="iidentityauthority-interface"></a><span data-ttu-id="9cddb-102">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="9cddb-102">IIdentityAuthority Interface</span></span>

<span data-ttu-id="9cddb-103">管理代码对象的标识键。</span><span class="sxs-lookup"><span data-stu-id="9cddb-103">Manages identity keys for code objects.</span></span>

## <a name="methods"></a><span data-ttu-id="9cddb-104">方法</span><span class="sxs-lookup"><span data-stu-id="9cddb-104">Methods</span></span>

|<span data-ttu-id="9cddb-105">方法</span><span class="sxs-lookup"><span data-stu-id="9cddb-105">Method</span></span>|<span data-ttu-id="9cddb-106">描述</span><span class="sxs-lookup"><span data-stu-id="9cddb-106">Description</span></span>|
|------------|-----------------|
|`IIdentityAuthority::AreDefinitionsEqual`|<span data-ttu-id="9cddb-107">获取一个值，该值指示两个指定[IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="9cddb-107">Gets a value that indicates whether the two specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreReferencesEqual`|<span data-ttu-id="9cddb-108">获取一个值，该值指示两个指定[IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="9cddb-108">Gets a value that indicates whether the two specified [IReferenceIdentity](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md) instances are equal.</span></span>|
|`IIdentityAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="9cddb-109">获取一个值，该值指示两个指定的字符串定义标识的表示形式是否相等。</span><span class="sxs-lookup"><span data-stu-id="9cddb-109">Gets a value that indicates whether the two specified string definition identity representations are equal.</span></span>|
|`IIdentityAuthority::AreTextualReferencesEqual`|<span data-ttu-id="9cddb-110">获取一个值，该值指示两个指定的字符串引用标识的表示形式是否相等。</span><span class="sxs-lookup"><span data-stu-id="9cddb-110">Gets a value that indicates whether the two specified string reference identity representations are equal.</span></span>|
|`IIdentityAuthority::CreateDefinition`|<span data-ttu-id="9cddb-111">获取一个指向到新`IDefinitionIdentity`实例，它表示当前作用域中的代码对象。</span><span class="sxs-lookup"><span data-stu-id="9cddb-111">Gets a pointer to a new `IDefinitionIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::CreateReference`|<span data-ttu-id="9cddb-112">获取一个指向到新`IReferenceIdentity`实例，它表示当前作用域中的代码对象。</span><span class="sxs-lookup"><span data-stu-id="9cddb-112">Gets a pointer to a new `IReferenceIdentity` instance that represents the code object in the current scope.</span></span>|
|`IIdentityAuthority::DefinitionToText`|<span data-ttu-id="9cddb-113">获取指定的带格式的字符串版本`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-113">Gets a formatted string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DefinitionToTextBuffer`|<span data-ttu-id="9cddb-114">使用指定的字符串版本填充指定的宽字符缓冲区`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-114">Fills the specified wide character buffer with a string version of the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="9cddb-115">获取一个值，该值指示是否指定`IDefinitionIdentity`和`IReferenceIdentity`实例引用相同的代码对象。</span><span class="sxs-lookup"><span data-stu-id="9cddb-115">Gets a value that indicates whether the specified `IDefinitionIdentity` and `IReferenceIdentity` instances refer to the same code object.</span></span>|
|`IIdentityAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="9cddb-116">获取一个值，该值指示指定的字符串是否引用相同的代码对象。</span><span class="sxs-lookup"><span data-stu-id="9cddb-116">Gets a value that indicates whether the specified strings refer to the same code object.</span></span>|
|`IIdentityAuthority::GenerateDefinitionKey`|<span data-ttu-id="9cddb-117">获取一个指针指向新创建的字符串键指定`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-117">Gets a pointer to a newly created string key for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::GenerateReferenceKey`|<span data-ttu-id="9cddb-118">获取一个指针指向新创建的字符串键指定`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-118">Gets a pointer to a newly created string key for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::HashDefinition`|<span data-ttu-id="9cddb-119">获取指定的哈希值`IDefinitionIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-119">Gets a hash value for the specified `IDefinitionIdentity`.</span></span>|
|`IIdentityAuthority::HashReference`|<span data-ttu-id="9cddb-120">获取指定的哈希值`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-120">Gets a hash value for the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToText`|<span data-ttu-id="9cddb-121">获取指定的带格式的字符串版本`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-121">Gets a formatted string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::ReferenceToTextBuffer`|<span data-ttu-id="9cddb-122">使用指定的字符串版本填充指定的宽字符缓冲区`IReferenceIdentity`。</span><span class="sxs-lookup"><span data-stu-id="9cddb-122">Fills the specified wide character buffer with a string version of the specified `IReferenceIdentity`.</span></span>|
|`IIdentityAuthority::TextToDefinition`|<span data-ttu-id="9cddb-123">获取到的接口指针`IDefinitionIdentity`实例生成指定的格式设置字符串。</span><span class="sxs-lookup"><span data-stu-id="9cddb-123">Gets an interface pointer to an `IDefinitionIdentity` instance generated from the specified formatted string.</span></span>|
|`IIdentityAuthority::TextToReference`|<span data-ttu-id="9cddb-124">获取到的接口指针`IReferenceIdentity`实例生成指定的格式设置字符串。</span><span class="sxs-lookup"><span data-stu-id="9cddb-124">Gets an interface pointer to an `IReferenceIdentity` instance generated from the specified formatted string.</span></span>|

## <a name="requirements"></a><span data-ttu-id="9cddb-125">要求</span><span class="sxs-lookup"><span data-stu-id="9cddb-125">Requirements</span></span>

<span data-ttu-id="9cddb-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9cddb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9cddb-127">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="9cddb-127">**Header:** Isolation.h</span></span>

<span data-ttu-id="9cddb-128">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cddb-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9cddb-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9cddb-129">See also</span></span>

- [<span data-ttu-id="9cddb-130">合成接口</span><span class="sxs-lookup"><span data-stu-id="9cddb-130">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
