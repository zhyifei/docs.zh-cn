---
title: "IMetaDataAssemblyEmit::DefineManifestResource 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="bad8a-102">IMetaDataAssemblyEmit::DefineManifestResource 方法</span><span class="sxs-lookup"><span data-stu-id="bad8a-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="bad8a-103">创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="bad8a-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bad8a-104">语法</span><span class="sxs-lookup"><span data-stu-id="bad8a-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bad8a-105">参数</span><span class="sxs-lookup"><span data-stu-id="bad8a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="bad8a-106">[in]资源的名称。</span><span class="sxs-lookup"><span data-stu-id="bad8a-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="bad8a-107">[in]类型的元数据标记`mdtFile`或`mdtAssemblyRef`映射到资源提供程序。</span><span class="sxs-lookup"><span data-stu-id="bad8a-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="bad8a-108">一个 NULL 值指示在其中嵌入的元数据文件是资源提供程序。</span><span class="sxs-lookup"><span data-stu-id="bad8a-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="bad8a-109">[in]到文件中的资源的开头的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bad8a-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="bad8a-110">对于独立文件中的资源，这将始终为零。</span><span class="sxs-lookup"><span data-stu-id="bad8a-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="bad8a-111">如果资源嵌入到 PE （可移植可执行文件） 文件中，这是资源 BLOB，cor.h 标头文件中指定的位置开始的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bad8a-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="bad8a-112">[in]指定的资源定义的属性设置的标志值按位组合。</span><span class="sxs-lookup"><span data-stu-id="bad8a-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="bad8a-113">[out]指向返回的元数据标记的指针。</span><span class="sxs-lookup"><span data-stu-id="bad8a-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bad8a-114">备注</span><span class="sxs-lookup"><span data-stu-id="bad8a-114">Remarks</span></span>  
 <span data-ttu-id="bad8a-115">一个`ManifestResource`必须为每个程序集的文件中实现的每个资源定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="bad8a-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bad8a-116">要求</span><span class="sxs-lookup"><span data-stu-id="bad8a-116">Requirements</span></span>  
 <span data-ttu-id="bad8a-117">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bad8a-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bad8a-118">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bad8a-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bad8a-119">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="bad8a-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bad8a-120">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bad8a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad8a-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bad8a-121">See Also</span></span>  
 [<span data-ttu-id="bad8a-122">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="bad8a-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
