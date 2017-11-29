---
title: "IMetaDataAssemblyEmit::DefineExportedType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineExportedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 245a485289335b096ee60a8eb3696a087e6871e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="fd86b-102">IMetaDataAssemblyEmit::DefineExportedType 方法</span><span class="sxs-lookup"><span data-stu-id="fd86b-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="fd86b-103">创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fd86b-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd86b-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd86b-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd86b-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd86b-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fd86b-106">[in]要导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="fd86b-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="fd86b-107">版本 1.1 的公共语言运行时，导出类型的名称必须完全匹配中给定的名称`TypeDef`类型。</span><span class="sxs-lookup"><span data-stu-id="fd86b-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="fd86b-108">[in]指定导出的类型实现了一个令牌。</span><span class="sxs-lookup"><span data-stu-id="fd86b-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="fd86b-109">有效的值和其关联的含义是：</span><span class="sxs-lookup"><span data-stu-id="fd86b-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="fd86b-110">`mdFile`类型是此程序集内的不同文件中实现的。</span><span class="sxs-lookup"><span data-stu-id="fd86b-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="fd86b-111">`mdAssemblyRef`类型是在不同的程序集中实现的。</span><span class="sxs-lookup"><span data-stu-id="fd86b-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="fd86b-112">`mdExportedTYpe`类型嵌套在其他类型。</span><span class="sxs-lookup"><span data-stu-id="fd86b-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="fd86b-113">`mdFileNil`类型在与清单相同的文件，并不是嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="fd86b-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="fd86b-114">[in]指定要导出的类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="fd86b-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="fd86b-115">在输入此值`TypeDef`中的文件，可实现类型并仅当该文件处于此程序集相关的表。</span><span class="sxs-lookup"><span data-stu-id="fd86b-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="fd86b-116">[in]按位组合[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)定义导出的类型的属性设置的枚举值。</span><span class="sxs-lookup"><span data-stu-id="fd86b-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="fd86b-117">[out]指向返回的元数据令牌，该值指示导出的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="fd86b-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd86b-118">备注</span><span class="sxs-lookup"><span data-stu-id="fd86b-118">Remarks</span></span>  
 <span data-ttu-id="fd86b-119">`ExportedType`必须为每个，则公开此程序集和实现中不包含清单的模块类型定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="fd86b-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd86b-120">要求</span><span class="sxs-lookup"><span data-stu-id="fd86b-120">Requirements</span></span>  
 <span data-ttu-id="fd86b-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd86b-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd86b-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fd86b-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd86b-123">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fd86b-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd86b-124">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd86b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd86b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd86b-125">See Also</span></span>  
 [<span data-ttu-id="fd86b-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="fd86b-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
