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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724ee01e91f1e9f4e34d2262610152a977ed4f53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206650"
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="3b69d-102">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="3b69d-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="3b69d-103">提供生成和比较键的应用程序标识和引用的方法。</span><span class="sxs-lookup"><span data-stu-id="3b69d-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b69d-104">方法</span><span class="sxs-lookup"><span data-stu-id="3b69d-104">Methods</span></span>  
  
|<span data-ttu-id="3b69d-105">方法</span><span class="sxs-lookup"><span data-stu-id="3b69d-105">Method</span></span>|<span data-ttu-id="3b69d-106">描述</span><span class="sxs-lookup"><span data-stu-id="3b69d-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="3b69d-107">获取一个值，该值指示两个指定[IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="3b69d-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="3b69d-108">可以传递标记值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="3b69d-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="3b69d-109">获取一个值，该值指示两个指定[IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="3b69d-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="3b69d-110">可以传递标记值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="3b69d-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="3b69d-111">获取一个值，该值指示是否相等的两个指定的字符串定义。</span><span class="sxs-lookup"><span data-stu-id="3b69d-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="3b69d-112">可以传递标记值 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="3b69d-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="3b69d-113">获取一个值，该值指示两个指定的字符串引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="3b69d-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="3b69d-114">可以传递标记值 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 忽略其各自的版本信息。</span><span class="sxs-lookup"><span data-stu-id="3b69d-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="3b69d-115">获取对新生成的接口指针`IDefinitionAppId`实例，它表示当前作用域中的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="3b69d-116">获取到新创建的接口指针`IReferenceAppId`，表示当前作用域中的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="3b69d-117">获取指定的字符串版本`IDefinitionAppId`，使用指定的标志值。</span><span class="sxs-lookup"><span data-stu-id="3b69d-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="3b69d-118">获取一个值，该值指示是否指定`IDefinitionAppId`和`IReferenceAppId`表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="3b69d-119">获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="3b69d-120">获取一个表示指定的字符串键`IDefinitionAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="3b69d-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="3b69d-121">获取一个表示指定的字符串键`IReferenceAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="3b69d-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="3b69d-122">获取指定的哈希键`IDefinitionAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="3b69d-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="3b69d-123">获取指定的哈希键`IReferenceAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="3b69d-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="3b69d-124">获取指定的字符串版本`IReferenceAppId`，使用指定的标志值。</span><span class="sxs-lookup"><span data-stu-id="3b69d-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="3b69d-125">获取到的接口指针`IDefinitionAppId`实例，它表示由指定的字符串参数引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="3b69d-126">获取到的接口指针`IReferenceAppId`实例，它表示由指定的字符串参数引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="3b69d-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3b69d-127">要求</span><span class="sxs-lookup"><span data-stu-id="3b69d-127">Requirements</span></span>  
 <span data-ttu-id="3b69d-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b69d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b69d-129">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="3b69d-129">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="3b69d-130">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3b69d-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b69d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b69d-131">See also</span></span>

- [<span data-ttu-id="3b69d-132">合成接口</span><span class="sxs-lookup"><span data-stu-id="3b69d-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
