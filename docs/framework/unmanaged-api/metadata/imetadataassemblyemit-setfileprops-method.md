---
title: IMetaDataAssemblyEmit::SetFileProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 25baa6ffda3d50915cc7898275d6a557c1b3e947
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176027"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="fe07a-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="fe07a-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="fe07a-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="fe07a-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe07a-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe07a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe07a-105">parameters</span><span class="sxs-lookup"><span data-stu-id="fe07a-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="fe07a-106">[在]指定要修改的`File`元数据结构的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="fe07a-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="fe07a-107">[在]指向与文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="fe07a-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="fe07a-108">[在]的大小（以字节为单位）。 `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="fe07a-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="fe07a-109">[在][CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值的位组合，用于指定文件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="fe07a-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe07a-110">备注</span><span class="sxs-lookup"><span data-stu-id="fe07a-110">Remarks</span></span>  
 <span data-ttu-id="fe07a-111">要创建`File`元数据结构，请使用[IMetaDataAssemblyEmit：:DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="fe07a-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe07a-112">要求</span><span class="sxs-lookup"><span data-stu-id="fe07a-112">Requirements</span></span>  
 <span data-ttu-id="fe07a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fe07a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe07a-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="fe07a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe07a-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fe07a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe07a-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe07a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe07a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe07a-117">See also</span></span>

- [<span data-ttu-id="fe07a-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="fe07a-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
