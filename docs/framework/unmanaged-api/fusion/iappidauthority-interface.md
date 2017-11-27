---
title: "IAppIdAuthority 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="88bd1-102">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="88bd1-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="88bd1-103">提供用于生成并比较应用程序标识和引用的密钥的方法。</span><span class="sxs-lookup"><span data-stu-id="88bd1-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="88bd1-104">方法</span><span class="sxs-lookup"><span data-stu-id="88bd1-104">Methods</span></span>  
  
|<span data-ttu-id="88bd1-105">方法</span><span class="sxs-lookup"><span data-stu-id="88bd1-105">Method</span></span>|<span data-ttu-id="88bd1-106">描述</span><span class="sxs-lookup"><span data-stu-id="88bd1-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="88bd1-107">获取一个值，该值指示两个指定[IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="88bd1-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="88bd1-108">你可以将传递 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="88bd1-109">获取一个值，该值指示两个指定[IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)实例是否相等。</span><span class="sxs-lookup"><span data-stu-id="88bd1-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="88bd1-110">你可以将传递 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="88bd1-111">获取一个值，该值指示两个指定的字符串定义是否相等。</span><span class="sxs-lookup"><span data-stu-id="88bd1-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="88bd1-112">你可以将传递 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="88bd1-113">获取一个值，该值指示两个指定的字符串引用是否相等。</span><span class="sxs-lookup"><span data-stu-id="88bd1-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="88bd1-114">你可以将传递 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 若要忽略及其各自的版本信息的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="88bd1-115">获取新生成的接口指针`IDefinitionAppId`表示当前范围中的程序集的实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="88bd1-116">获取新创建的接口指针`IReferenceAppId`，它表示当前范围中的程序集。</span><span class="sxs-lookup"><span data-stu-id="88bd1-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="88bd1-117">获取指定的字符串版本`IDefinitionAppId`，使用指定的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="88bd1-118">获取一个值，该值指示是否指定`IDefinitionAppId`和`IReferenceAppId`表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="88bd1-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="88bd1-119">获取一个值，该值指示指定的定义字符串和引用字符串是否表示相同的程序集。</span><span class="sxs-lookup"><span data-stu-id="88bd1-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="88bd1-120">获取一个表示指定的字符串键`IDefinitionAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="88bd1-121">获取一个表示指定的字符串键`IReferenceAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="88bd1-122">获取指定的哈希键`IDefinitionAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="88bd1-123">获取指定的哈希键`IReferenceAppId`实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="88bd1-124">获取指定的字符串版本`IReferenceAppId`，使用指定的标志值。</span><span class="sxs-lookup"><span data-stu-id="88bd1-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="88bd1-125">获取到的接口指针`IDefinitionAppId`表示由指定的字符串参数引用的程序集的实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="88bd1-126">获取到的接口指针`IReferenceAppId`表示由指定的字符串参数引用的程序集的实例。</span><span class="sxs-lookup"><span data-stu-id="88bd1-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="88bd1-127">要求</span><span class="sxs-lookup"><span data-stu-id="88bd1-127">Requirements</span></span>  
 <span data-ttu-id="88bd1-128">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88bd1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88bd1-129">**标头：** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="88bd1-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="88bd1-130">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88bd1-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88bd1-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88bd1-131">See Also</span></span>  
 [<span data-ttu-id="88bd1-132">合成接口</span><span class="sxs-lookup"><span data-stu-id="88bd1-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
