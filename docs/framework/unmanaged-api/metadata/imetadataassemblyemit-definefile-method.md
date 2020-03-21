---
title: IMetaDataAssemblyEmit::DefineFile 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
ms.openlocfilehash: cabd6a47e5d6fc2a4cea87b16d349d9c778b3507
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176053"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="7bd84-102">IMetaDataAssemblyEmit::DefineFile 方法</span><span class="sxs-lookup"><span data-stu-id="7bd84-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="7bd84-103">创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7bd84-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bd84-104">语法</span><span class="sxs-lookup"><span data-stu-id="7bd84-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,
    [in]  const void     *pbHashValue,
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bd84-105">parameters</span><span class="sxs-lookup"><span data-stu-id="7bd84-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="7bd84-106">[在]要使用的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7bd84-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="7bd84-107">[在]指向与程序集关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="7bd84-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="7bd84-108">[在]的大小（以字节为单位）。 `pbHashValue`</span><span class="sxs-lookup"><span data-stu-id="7bd84-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="7bd84-109">[在]指定属性设置的值的`FileFlags`位组合。</span><span class="sxs-lookup"><span data-stu-id="7bd84-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="7bd84-110">[出]指向返回`File`的令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="7bd84-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bd84-111">备注</span><span class="sxs-lookup"><span data-stu-id="7bd84-111">Remarks</span></span>  
 <span data-ttu-id="7bd84-112">必须`File`为生成此程序集时属于此程序集的每个文件定义一个元数据结构，不包括包含元数据的文件。</span><span class="sxs-lookup"><span data-stu-id="7bd84-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bd84-113">要求</span><span class="sxs-lookup"><span data-stu-id="7bd84-113">Requirements</span></span>  
 <span data-ttu-id="7bd84-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7bd84-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bd84-115">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="7bd84-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bd84-116">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7bd84-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bd84-117">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bd84-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bd84-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bd84-118">See also</span></span>

- [<span data-ttu-id="7bd84-119">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="7bd84-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
