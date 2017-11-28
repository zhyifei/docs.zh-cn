---
title: "IMetaDataAssemblyEmit::DefineFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineFile
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f3be44603eb16c6e74b34c0f569fc5bb11264ca0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="243de-102">IMetaDataAssemblyEmit::DefineFile 方法</span><span class="sxs-lookup"><span data-stu-id="243de-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="243de-103">创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="243de-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243de-104">语法</span><span class="sxs-lookup"><span data-stu-id="243de-104">Syntax</span></span>  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="243de-105">参数</span><span class="sxs-lookup"><span data-stu-id="243de-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="243de-106">[in]要使用的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="243de-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="243de-107">[in]指向与程序集关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="243de-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="243de-108">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="243de-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="243de-109">[in]按位组合`FileFlags`指定属性设置的值。</span><span class="sxs-lookup"><span data-stu-id="243de-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="243de-110">[out]指向返回的指针`File`令牌。</span><span class="sxs-lookup"><span data-stu-id="243de-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="243de-111">备注</span><span class="sxs-lookup"><span data-stu-id="243de-111">Remarks</span></span>  
 <span data-ttu-id="243de-112">一个`File`必须为每个文件的已生成此程序集，不包括包含的元数据的文件时此程序集的一部分定义元数据结构。</span><span class="sxs-lookup"><span data-stu-id="243de-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="243de-113">要求</span><span class="sxs-lookup"><span data-stu-id="243de-113">Requirements</span></span>  
 <span data-ttu-id="243de-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="243de-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="243de-115">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="243de-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="243de-116">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="243de-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="243de-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="243de-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243de-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="243de-118">See Also</span></span>  
 [<span data-ttu-id="243de-119">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="243de-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
