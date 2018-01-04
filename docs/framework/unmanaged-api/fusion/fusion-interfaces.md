---
title: "合成接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- interfaces [.NET Framework fusion]
- fusion interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], fusion
ms.assetid: e2cf98b7-40c1-4f74-86c7-8a76dd9da677
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9226eba1b9f03138180430b2abb960f43f4b4260
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="fusion-interfaces"></a><span data-ttu-id="6c25c-102">合成接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-102">Fusion Interfaces</span></span>
<span data-ttu-id="6c25c-103">本部分描述合成 API 使用来访问应用程序的资源的属性并查找这些应用程序资源的正确版本的非托管的接口。</span><span class="sxs-lookup"><span data-stu-id="6c25c-103">This section describes the unmanaged interfaces that the fusion API uses to access the properties of an application's resources and to locate the correct versions of those resources for the application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c25c-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="6c25c-104">In This Section</span></span>  
 [<span data-ttu-id="6c25c-105">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-105">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 <span data-ttu-id="6c25c-106">提供用于生成并比较应用程序标识和引用的密钥的方法。</span><span class="sxs-lookup"><span data-stu-id="6c25c-106">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
 [<span data-ttu-id="6c25c-107">IAssemblyCache 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-107">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 <span data-ttu-id="6c25c-108">提供的表示形式的全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="6c25c-108">Provides a representation of the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6c25c-109">IAssemblyCacheItem 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-109">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)  
 <span data-ttu-id="6c25c-110">表示全局程序集缓存中的单个程序集。</span><span class="sxs-lookup"><span data-stu-id="6c25c-110">Represents a single assembly in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6c25c-111">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-111">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)  
 <span data-ttu-id="6c25c-112">表示为数组的枚举`IAssemblyName`对象。</span><span class="sxs-lookup"><span data-stu-id="6c25c-112">Represents an enumerator for an array of `IAssemblyName` objects.</span></span>  
  
 [<span data-ttu-id="6c25c-113">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-113">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 <span data-ttu-id="6c25c-114">提供用于描述和使用程序集的唯一标识的方法。</span><span class="sxs-lookup"><span data-stu-id="6c25c-114">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
 [<span data-ttu-id="6c25c-115">IDefinitionAppId 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-115">IDefinitionAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md)  
 <span data-ttu-id="6c25c-116">表示在当前范围内定义应用程序的代码的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6c25c-116">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6c25c-117">IDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-117">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)  
 <span data-ttu-id="6c25c-118">表示在当前范围内定义应用程序的代码的唯一签名。</span><span class="sxs-lookup"><span data-stu-id="6c25c-118">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6c25c-119">IEnumDefinitionIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-119">IEnumDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md)  
 <span data-ttu-id="6c25c-120">用作的集合的枚举数`IDefinitionIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="6c25c-120">Serves as the enumerator for a collection of `IDefinitionIdentity` objects.</span></span>  
  
 [<span data-ttu-id="6c25c-121">IEnumIDENTITY_ATTRIBUTE 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-121">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)  
 <span data-ttu-id="6c25c-122">用作当前范围中的代码对象的属性的枚举数。</span><span class="sxs-lookup"><span data-stu-id="6c25c-122">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
 [<span data-ttu-id="6c25c-123">IEnumReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-123">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 <span data-ttu-id="6c25c-124">用作的集合的枚举数`IReferenceIdentity`对象。</span><span class="sxs-lookup"><span data-stu-id="6c25c-124">Serves as an enumerator for a collection of `IReferenceIdentity` objects.</span></span>  
  
 [<span data-ttu-id="6c25c-125">IIdentityAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-125">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)  
 <span data-ttu-id="6c25c-126">管理代码对象的标识键。</span><span class="sxs-lookup"><span data-stu-id="6c25c-126">Manages identity keys for code objects.</span></span>  
  
 [<span data-ttu-id="6c25c-127">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-127">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 <span data-ttu-id="6c25c-128">表示引用的程序集安装到全局程序集缓存中的枚举数。</span><span class="sxs-lookup"><span data-stu-id="6c25c-128">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6c25c-129">IInstallReferenceItem 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-129">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 <span data-ttu-id="6c25c-130">表示安装在全局程序集缓存中的项。</span><span class="sxs-lookup"><span data-stu-id="6c25c-130">Represents an item installed in the global assembly cache.</span></span>  
  
 [<span data-ttu-id="6c25c-131">IReferenceAppId 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-131">IReferenceAppId Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md)  
 <span data-ttu-id="6c25c-132">表示当前范围中的应用程序的唯一标识符的引用。</span><span class="sxs-lookup"><span data-stu-id="6c25c-132">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
 [<span data-ttu-id="6c25c-133">IReferenceIdentity 接口</span><span class="sxs-lookup"><span data-stu-id="6c25c-133">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)  
 <span data-ttu-id="6c25c-134">表示对代码对象的唯一签名的引用。</span><span class="sxs-lookup"><span data-stu-id="6c25c-134">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6c25c-135">参考</span><span class="sxs-lookup"><span data-stu-id="6c25c-135">Reference</span></span>  
 <xref:System.Reflection>  
  
 <xref:System.Reflection.Emit>  
  
## <a name="related-sections"></a><span data-ttu-id="6c25c-136">相关章节</span><span class="sxs-lookup"><span data-stu-id="6c25c-136">Related Sections</span></span>  
 [<span data-ttu-id="6c25c-137">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="6c25c-137">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
  
 [<span data-ttu-id="6c25c-138">合成枚举</span><span class="sxs-lookup"><span data-stu-id="6c25c-138">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)  
  
 [<span data-ttu-id="6c25c-139">合成结构</span><span class="sxs-lookup"><span data-stu-id="6c25c-139">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
