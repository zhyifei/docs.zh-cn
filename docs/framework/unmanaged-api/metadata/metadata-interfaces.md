---
title: 元数据接口
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 4672cb813cec4a127f7888a2273eb26c3f34c3d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431584"
---
# <a name="metadata-interfaces"></a><span data-ttu-id="f8436-102">元数据接口</span><span class="sxs-lookup"><span data-stu-id="f8436-102">Metadata Interfaces</span></span>
<span data-ttu-id="f8436-103">本节描述非托管接口，这些接口提供对由 .NET Framework 类型、方法、字段等公开的元数据的访问。</span><span class="sxs-lookup"><span data-stu-id="f8436-103">This section describes the unmanaged interfaces that provide access to the metadata exposed by the .NET Framework types, methods, fields, and so on.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8436-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="f8436-104">In This Section</span></span>  
 [<span data-ttu-id="f8436-105">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-105">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 <span data-ttu-id="f8436-106">提供用于动态代码编译的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-106">Provides methods for dynamic code compilation.</span></span>  
  
 [<span data-ttu-id="f8436-107">IHostFilter 方法</span><span class="sxs-lookup"><span data-stu-id="f8436-107">IHostFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/ihostfilter-interface.md)  
 <span data-ttu-id="f8436-108">提供运行时主机用于标记待处理的元数据标记的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-108">Provides a method for the run-time host to mark metadata tokens for processing.</span></span>  
  
 [<span data-ttu-id="f8436-109">IMapToken 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-109">IMapToken Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)  
 <span data-ttu-id="f8436-110">提供导入的和发出的元数据签名之间的映射功能。</span><span class="sxs-lookup"><span data-stu-id="f8436-110">Provides mapping capabilities between imported and emitted metadata signatures.</span></span>  
  
 [<span data-ttu-id="f8436-111">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-111">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 <span data-ttu-id="f8436-112">提供支持公共语言运行时 (CLR) 用于解析和使用资源的自描述模型的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-112">Provides methods that support the self-description model used by the common language runtime (CLR) to resolve and consume resources.</span></span>  
  
 [<span data-ttu-id="f8436-113">IMetaDataAssemblyImport 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 <span data-ttu-id="f8436-114">提供访问和检查程序集清单内容的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-114">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
 [<span data-ttu-id="f8436-115">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-115">IMetaDataConverter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-interface.md)  
 <span data-ttu-id="f8436-116">提供将类型库映射到其元数据签名并进行相互转换的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-116">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
 [<span data-ttu-id="f8436-117">IMetaDataDispenser 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-117">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 <span data-ttu-id="f8436-118">`IMetaDataDispenser` 已过时。</span><span class="sxs-lookup"><span data-stu-id="f8436-118">`IMetaDataDispenser` is obsolete.</span></span> <span data-ttu-id="f8436-119">请改用 `IMetaDataDispenserEx` 。</span><span class="sxs-lookup"><span data-stu-id="f8436-119">Use `IMetaDataDispenserEx` instead.</span></span>  
  
 [<span data-ttu-id="f8436-120">IMetaDataDispenserEx 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-120">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 <span data-ttu-id="f8436-121">提供映射用于创建或修改元数据的内存区域的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-121">Provides methods that map areas of memory for creating or modifying metadata.</span></span>  
  
 [<span data-ttu-id="f8436-122">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f8436-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 <span data-ttu-id="f8436-123">提供创建、修改和存储与当前定义的范围中的程序集相关的元数据的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-123">Provides methods to create, modify and store metadata about the assembly in the currently defined scope.</span></span>  
  
 [<span data-ttu-id="f8436-124">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f8436-124">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 <span data-ttu-id="f8436-125">提供用于定义和修改方法的元数据签名和带有 <xref:System.Type?displayProperty=nameWithType> 类型的参数的构造函数的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-125">Provides methods for defining and modifying the metadata signatures of methods and constructors with parameters of type <xref:System.Type?displayProperty=nameWithType>.</span></span>  
  
 [<span data-ttu-id="f8436-126">IMetaDataError 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-126">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)  
 <span data-ttu-id="f8436-127">提供用于在解析程序集的元数据签名期间报告错误的回调机制。</span><span class="sxs-lookup"><span data-stu-id="f8436-127">Provides a callback mechanism for reporting errors during the resolution of the metadata signature for an assembly.</span></span>  
  
 [<span data-ttu-id="f8436-128">IMetaDataFilter 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-128">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)  
 <span data-ttu-id="f8436-129">提供用于标记和筛选元数据标记以避免重复已进行的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-129">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
 [<span data-ttu-id="f8436-130">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 <span data-ttu-id="f8436-131">提供用于从其他程序集导入和操作类型的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-131">Provides methods for importing and manipulating types from other assemblies.</span></span>  
  
 [<span data-ttu-id="f8436-132">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-132">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 <span data-ttu-id="f8436-133">扩展 `IMetaDataImport` 以提供使用泛型类型的功能。</span><span class="sxs-lookup"><span data-stu-id="f8436-133">Extends `IMetaDataImport` to provide the capability of working with generic types.</span></span>  
  
 [<span data-ttu-id="f8436-134">IMetaDataInfo 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-134">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 <span data-ttu-id="f8436-135">提供一种方法，使用此方法可获取关于将元数据从磁盘文件映射到内存中的信息。</span><span class="sxs-lookup"><span data-stu-id="f8436-135">Provides a method that gets information about the mapping of metadata from an on-disk file into memory.</span></span>  
  
 [<span data-ttu-id="f8436-136">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-136">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 <span data-ttu-id="f8436-137">提供存储和检索表中元数据信息的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-137">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
 [<span data-ttu-id="f8436-138">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-138">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 <span data-ttu-id="f8436-139">扩展 `IMetaDataTables` 以包含用于处理元数据流的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-139">Extends `IMetaDataTables` to include methods for working with metadata streams.</span></span>  
  
 [<span data-ttu-id="f8436-140">IMetaDataValidate 接口</span><span class="sxs-lookup"><span data-stu-id="f8436-140">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)  
 <span data-ttu-id="f8436-141">提供验证元数据签名的方法。</span><span class="sxs-lookup"><span data-stu-id="f8436-141">Provides methods to use for validation of metadata signatures.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f8436-142">相关章节</span><span class="sxs-lookup"><span data-stu-id="f8436-142">Related Sections</span></span>  
 [<span data-ttu-id="f8436-143">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="f8436-143">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)  
  
 [<span data-ttu-id="f8436-144">Metadata 枚举</span><span class="sxs-lookup"><span data-stu-id="f8436-144">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
  
 [<span data-ttu-id="f8436-145">元数据结构</span><span class="sxs-lookup"><span data-stu-id="f8436-145">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)  
  
 [<span data-ttu-id="f8436-146">元数据联合</span><span class="sxs-lookup"><span data-stu-id="f8436-146">Metadata Unions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-unions.md)
