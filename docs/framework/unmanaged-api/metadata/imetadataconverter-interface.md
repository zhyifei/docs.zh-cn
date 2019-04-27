---
title: IMetaDataConverter 接口
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d3377617ddd6b82ad88d22f6ffda04b1d6ae837
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904743"
---
# <a name="imetadataconverter-interface"></a><span data-ttu-id="27ac8-102">IMetaDataConverter 接口</span><span class="sxs-lookup"><span data-stu-id="27ac8-102">IMetaDataConverter Interface</span></span>
<span data-ttu-id="27ac8-103">提供将类型库映射到其元数据签名并进行相互转换的方法。</span><span class="sxs-lookup"><span data-stu-id="27ac8-103">Provides methods to map type libraries to their metadata signatures, and to convert from one to the other.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27ac8-104">方法</span><span class="sxs-lookup"><span data-stu-id="27ac8-104">Methods</span></span>  
  
|<span data-ttu-id="27ac8-105">方法</span><span class="sxs-lookup"><span data-stu-id="27ac8-105">Method</span></span>|<span data-ttu-id="27ac8-106">描述</span><span class="sxs-lookup"><span data-stu-id="27ac8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27ac8-107">GetMetaDataFromTypeInfo 方法</span><span class="sxs-lookup"><span data-stu-id="27ac8-107">GetMetaDataFromTypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|<span data-ttu-id="27ac8-108">获取一个指向[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)实例，它表示由指定引用的类型库的元数据签名`ITypeInfo`实例。</span><span class="sxs-lookup"><span data-stu-id="27ac8-108">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature for the type library referenced by the specified `ITypeInfo` instance.</span></span>|  
|[<span data-ttu-id="27ac8-109">GetMetaDataFromTypeLib 方法</span><span class="sxs-lookup"><span data-stu-id="27ac8-109">GetMetaDataFromTypeLib Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|<span data-ttu-id="27ac8-110">获取一个指向`IMetaDataImport`实例，它表示由指定的类型库的元数据签名`ITypeLib`实例。</span><span class="sxs-lookup"><span data-stu-id="27ac8-110">Gets a pointer to an `IMetaDataImport` instance that represents the metadata signature for the type library represented by the specified `ITypeLib` instance.</span></span>|  
|[<span data-ttu-id="27ac8-111">GetTypeLibFromMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="27ac8-111">GetTypeLibFromMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|<span data-ttu-id="27ac8-112">获取一个指向`ITypeLib`实例，它表示具有指定的模块和库名称的类型库。</span><span class="sxs-lookup"><span data-stu-id="27ac8-112">Gets a pointer to an `ITypeLib` instance that represents the type library that has the specified module and library names.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27ac8-113">要求</span><span class="sxs-lookup"><span data-stu-id="27ac8-113">Requirements</span></span>  
 <span data-ttu-id="27ac8-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27ac8-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27ac8-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27ac8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27ac8-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="27ac8-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27ac8-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27ac8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27ac8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="27ac8-118">See also</span></span>

- [<span data-ttu-id="27ac8-119">元数据接口</span><span class="sxs-lookup"><span data-stu-id="27ac8-119">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="27ac8-120">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="27ac8-120">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
