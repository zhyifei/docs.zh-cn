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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177884"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="a8611-102">IMetaDataAssemblyEmit::DefineExportedType 方法</span><span class="sxs-lookup"><span data-stu-id="a8611-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="a8611-103">创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="a8611-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8611-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8611-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8611-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a8611-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a8611-106">[在]要导出的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="a8611-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="a8611-107">对于通用语言运行时的版本 1.1，导出类型的名称必须与 类型中`TypeDef`给出的名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a8611-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="a8611-108">[在]指定导出类型的实现位置的令牌。</span><span class="sxs-lookup"><span data-stu-id="a8611-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="a8611-109">有效值及其相关含义包括：</span><span class="sxs-lookup"><span data-stu-id="a8611-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="a8611-110">`mdFile`该类型在此程序集中的其他文件中实现。</span><span class="sxs-lookup"><span data-stu-id="a8611-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="a8611-111">`mdAssemblyRef`该类型在不同的程序集中实现。</span><span class="sxs-lookup"><span data-stu-id="a8611-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="a8611-112">`mdExportedTYpe`类型嵌套在某种其他类型中。</span><span class="sxs-lookup"><span data-stu-id="a8611-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="a8611-113">`mdFileNil`类型与清单位于同一文件中，不是嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="a8611-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="a8611-114">[在]指定要导出的类型的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="a8611-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="a8611-115">此值在文件中实现该类型的`TypeDef`表中输入，并且仅当该文件位于此程序集中时才相关。</span><span class="sxs-lookup"><span data-stu-id="a8611-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="a8611-116">[在][CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md)枚举值的位组合，用于定义导出类型的属性设置。</span><span class="sxs-lookup"><span data-stu-id="a8611-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="a8611-117">[出]指向返回的元数据令牌的指针，指示导出的类型。</span><span class="sxs-lookup"><span data-stu-id="a8611-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8611-118">备注</span><span class="sxs-lookup"><span data-stu-id="a8611-118">Remarks</span></span>  
 <span data-ttu-id="a8611-119">必须`ExportedType`为此程序集公开的并且在包含清单的模块以外的模块中实现的每一种类型定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="a8611-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8611-120">要求</span><span class="sxs-lookup"><span data-stu-id="a8611-120">Requirements</span></span>  
 <span data-ttu-id="a8611-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8611-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8611-122">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a8611-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8611-123">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a8611-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8611-124">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8611-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8611-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8611-125">See also</span></span>

- [<span data-ttu-id="a8611-126">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="a8611-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
