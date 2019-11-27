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
ms.openlocfilehash: 0b7ca6f9878ed2fa2d90ea93e5101f0a66ec2d5e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440205"
---
# <a name="imetadataassemblyemitdefinefile-method"></a><span data-ttu-id="f01ca-102">IMetaDataAssemblyEmit::DefineFile 方法</span><span class="sxs-lookup"><span data-stu-id="f01ca-102">IMetaDataAssemblyEmit::DefineFile Method</span></span>
<span data-ttu-id="f01ca-103">创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="f01ca-103">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f01ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="f01ca-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f01ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="f01ca-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f01ca-106">中要使用的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="f01ca-106">[in] The name of the file to be consumed.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="f01ca-107">中指向与程序集关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="f01ca-107">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="f01ca-108">中`pbHashValue`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="f01ca-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="f01ca-109">中指定属性设置 `FileFlags` 值的按位组合。</span><span class="sxs-lookup"><span data-stu-id="f01ca-109">[in] A bitwise combination of `FileFlags` values that specify property settings.</span></span>  
  
 `pmdf`  
 <span data-ttu-id="f01ca-110">弄指向返回的 `File` 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="f01ca-110">[out] A pointer to the returned `File` token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f01ca-111">备注</span><span class="sxs-lookup"><span data-stu-id="f01ca-111">Remarks</span></span>  
 <span data-ttu-id="f01ca-112">必须在生成此程序集时为作为此程序集的一部分的每个文件定义一个 `File` 元数据结构，其中不包括包含元数据的文件。</span><span class="sxs-lookup"><span data-stu-id="f01ca-112">One `File` metadata structure must be defined for each file that was part of this assembly at the time that this assembly was built, excluding the file that contains the metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f01ca-113">要求</span><span class="sxs-lookup"><span data-stu-id="f01ca-113">Requirements</span></span>  
 <span data-ttu-id="f01ca-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f01ca-114">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f01ca-115">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f01ca-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f01ca-116">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f01ca-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f01ca-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f01ca-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f01ca-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f01ca-118">See also</span></span>

- [<span data-ttu-id="f01ca-119">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f01ca-119">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
