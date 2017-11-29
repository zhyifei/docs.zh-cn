---
title: "IMetaDataConverter 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="6b133-102">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="6b133-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="6b133-103">提供将类型库映射到其元数据签名并进行相互转换的方法。</span><span class="sxs-lookup"><span data-stu-id="6b133-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b133-104">方法</span><span class="sxs-lookup"><span data-stu-id="6b133-104">Methods</span></span>  
  
|<span data-ttu-id="6b133-105">方法</span><span class="sxs-lookup"><span data-stu-id="6b133-105">Method</span></span>|<span data-ttu-id="6b133-106">描述</span><span class="sxs-lookup"><span data-stu-id="6b133-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b133-107">GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="6b133-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="6b133-108">获取一个指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定引用的类型库的元数据签名`ITypeInfo`实例。</span><span class="sxs-lookup"><span data-stu-id="6b133-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="6b133-109">GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="6b133-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="6b133-110">获取一个指向`IMetaDataImport`实例，它表示由指定的类型库的元数据签名`ITypeLib`实例。</span><span class="sxs-lookup"><span data-stu-id="6b133-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="6b133-111">GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="6b133-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="6b133-112">获取一个指向`ITypeLib`表示具有指定的模块和库名称的类型库的实例。</span><span class="sxs-lookup"><span data-stu-id="6b133-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b133-113">要求</span><span class="sxs-lookup"><span data-stu-id="6b133-113">Requirements</span></span>  
 <span data-ttu-id="6b133-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b133-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b133-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b133-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b133-116">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6b133-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b133-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b133-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b133-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b133-118">See Also</span></span>  
 [<span data-ttu-id="6b133-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="6b133-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="6b133-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6b133-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
