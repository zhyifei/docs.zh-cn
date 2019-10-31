---
title: IAppIdAuthority 接口
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: 004e4f70e3385e7a71c356cce38e64d0253dcfa4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127132"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="02ec7-102">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="02ec7-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="02ec7-103">提供一些方法，这些方法可为应用程序标识和引用生成和比较键。</span><span class="sxs-lookup"><span data-stu-id="02ec7-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02ec7-104">方法</span><span class="sxs-lookup"><span data-stu-id="02ec7-104">Methods</span></span>  
  
|<span data-ttu-id="02ec7-105">方法</span><span class="sxs-lookup"><span data-stu-id="02ec7-105">Method</span></span>|<span data-ttu-id="02ec7-106">描述</span><span class="sxs-lookup"><span data-stu-id="02ec7-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="02ec7-107">获取一个值，该值指示两个指定的[IDefinitionAppId](idefinitionappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="02ec7-107">Gets a value that indicates whether the two specified [IDefinitionAppId](idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="02ec7-108">可以传递标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="02ec7-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="02ec7-109">获取一个值，该值指示两个指定的[IReferenceAppId](ireferenceappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="02ec7-109">Gets a value that indicates whether the two specified [IReferenceAppId](ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="02ec7-110">可以传递标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="02ec7-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="02ec7-111">获取一个值，该值指示两个指定的字符串定义是否相等。</span><span class="sxs-lookup"><span data-stu-id="02ec7-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="02ec7-112">可以传递标志值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="02ec7-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="02ec7-113">获取一个值，该值指示两个指定的字符串引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="02ec7-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="02ec7-114">可以传递标志值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 来忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="02ec7-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="02ec7-115">获取一个接口指针，该指针指向表示当前范围内的程序集的新生成的 `IDefinitionAppId` 实例。</span><span class="sxs-lookup"><span data-stu-id="02ec7-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="02ec7-116">获取一个指向新创建的 `IReferenceAppId` 的接口指针，该指针表示当前范围内的程序集。</span><span class="sxs-lookup"><span data-stu-id="02ec7-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="02ec7-117">使用指定的标志值获取指定 `IDefinitionAppId`的字符串版本。</span><span class="sxs-lookup"><span data-stu-id="02ec7-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="02ec7-118">获取一个值，该值指示指定的 `IDefinitionAppId` 和 `IReferenceAppId` 是否表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="02ec7-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="02ec7-119">获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="02ec7-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="02ec7-120">获取表示指定的 `IDefinitionAppId` 实例的字符串键。</span><span class="sxs-lookup"><span data-stu-id="02ec7-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="02ec7-121">获取表示指定的 `IReferenceAppId` 实例的字符串键。</span><span class="sxs-lookup"><span data-stu-id="02ec7-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="02ec7-122">获取指定 `IDefinitionAppId` 实例的哈希键。</span><span class="sxs-lookup"><span data-stu-id="02ec7-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="02ec7-123">获取指定 `IReferenceAppId` 实例的哈希键。</span><span class="sxs-lookup"><span data-stu-id="02ec7-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="02ec7-124">使用指定的标志值获取指定 `IReferenceAppId`的字符串版本。</span><span class="sxs-lookup"><span data-stu-id="02ec7-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="02ec7-125">获取一个指向 `IDefinitionAppId` 实例的接口指针，该实例表示指定的字符串键所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="02ec7-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="02ec7-126">获取一个指向 `IReferenceAppId` 实例的接口指针，该实例表示指定的字符串键所引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="02ec7-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02ec7-127">要求</span><span class="sxs-lookup"><span data-stu-id="02ec7-127">Requirements</span></span>  
 <span data-ttu-id="02ec7-128">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="02ec7-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02ec7-129">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="02ec7-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="02ec7-130">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02ec7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02ec7-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="02ec7-131">See also</span></span>

- [<span data-ttu-id="02ec7-132">合成接口</span><span class="sxs-lookup"><span data-stu-id="02ec7-132">Fusion Interfaces</span></span>](fusion-interfaces.md)
