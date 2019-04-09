---
title: IMetaDataAssemblyEmit::DefineExportedType 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e89fda72371f197efeeeef8f31ec396c334cfcb2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122026"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="d49cc-102">IMetaDataAssemblyEmit::DefineExportedType 方法</span><span class="sxs-lookup"><span data-stu-id="d49cc-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="d49cc-103">创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d49cc-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d49cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="d49cc-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d49cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="d49cc-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="d49cc-106">[in]要导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="d49cc-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="d49cc-107">为版本 1.1 的公共语言运行时，导出的类型的名称必须与中给定的名称完全匹配`TypeDef`的类型。</span><span class="sxs-lookup"><span data-stu-id="d49cc-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="d49cc-108">[in]指定导出的类型实现的位置标记。</span><span class="sxs-lookup"><span data-stu-id="d49cc-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="d49cc-109">有效的值和其关联的含义是：</span><span class="sxs-lookup"><span data-stu-id="d49cc-109">The valid values and their associated meanings are:</span></span>  
  
-   `mdFile` <span data-ttu-id="d49cc-110">类型是此程序集内的不同文件中实现的。</span><span class="sxs-lookup"><span data-stu-id="d49cc-110">The type is implemented in a different file within this assembly.</span></span>  
  
-   `mdAssemblyRef` <span data-ttu-id="d49cc-111">类型是在不同的程序集中实现的。</span><span class="sxs-lookup"><span data-stu-id="d49cc-111">The type is implemented in a different assembly.</span></span>  
  
-   `mdExportedTYpe` <span data-ttu-id="d49cc-112">该类型嵌套在其他类型。</span><span class="sxs-lookup"><span data-stu-id="d49cc-112">The type is nested within some other type.</span></span>  
  
-   `mdFileNil` <span data-ttu-id="d49cc-113">类型是在清单的同一个文件中并不是嵌套的类型。</span><span class="sxs-lookup"><span data-stu-id="d49cc-113">The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="d49cc-114">[in]指定要导出的类型的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="d49cc-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="d49cc-115">此值中输入`TypeDef`将实现类型，将只适用于该文件是在此程序集中的文件中的表。</span><span class="sxs-lookup"><span data-stu-id="d49cc-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="d49cc-116">[in]按位组合[CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)定义导出的类型的属性设置的枚举值。</span><span class="sxs-lookup"><span data-stu-id="d49cc-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="d49cc-117">[out]指向返回的元数据令牌，该值指示导出的类型的指针。</span><span class="sxs-lookup"><span data-stu-id="d49cc-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d49cc-118">备注</span><span class="sxs-lookup"><span data-stu-id="d49cc-118">Remarks</span></span>  
 <span data-ttu-id="d49cc-119">`ExportedType`必须为每种类型公开的此程序集和实现不包含清单的模块中定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="d49cc-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d49cc-120">要求</span><span class="sxs-lookup"><span data-stu-id="d49cc-120">Requirements</span></span>  
 <span data-ttu-id="d49cc-121">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d49cc-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d49cc-122">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d49cc-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d49cc-123">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d49cc-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d49cc-124">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d49cc-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d49cc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d49cc-125">See also</span></span>

- [<span data-ttu-id="d49cc-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d49cc-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
