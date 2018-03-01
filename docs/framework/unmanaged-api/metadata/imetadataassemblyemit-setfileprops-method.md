---
title: "IMetaDataAssemblyEmit::SetFileProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bc0f0b2cbc22a7e9d6dcac6e359f36f365d368af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="d3ed8-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="d3ed8-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="d3ed8-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3ed8-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3ed8-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3ed8-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3ed8-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="d3ed8-106">[in]指定的元数据标记`File`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="d3ed8-107">[in]指向与文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="d3ed8-108">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="d3ed8-109">[in]按位组合[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)指定的文件的各种属性的值。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3ed8-110">备注</span><span class="sxs-lookup"><span data-stu-id="d3ed8-110">Remarks</span></span>  
 <span data-ttu-id="d3ed8-111">若要创建`File`元数据结构，使用[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3ed8-112">惠?</span><span class="sxs-lookup"><span data-stu-id="d3ed8-112">Requirements</span></span>  
 <span data-ttu-id="d3ed8-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3ed8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3ed8-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3ed8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3ed8-115">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3ed8-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3ed8-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3ed8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3ed8-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3ed8-117">See Also</span></span>  
 [<span data-ttu-id="d3ed8-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="d3ed8-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
