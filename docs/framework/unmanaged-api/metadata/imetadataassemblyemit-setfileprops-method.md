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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a04162a870833ff409c93527733e2380d9c3eed2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474726"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="6b009-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="6b009-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="6b009-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="6b009-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b009-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b009-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b009-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b009-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="6b009-106">[in]指定的元数据标记`File`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="6b009-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="6b009-107">[in]指向与文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="6b009-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="6b009-108">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="6b009-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="6b009-109">[in]按位组合[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)指定文件的各种属性的值。</span><span class="sxs-lookup"><span data-stu-id="6b009-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b009-110">备注</span><span class="sxs-lookup"><span data-stu-id="6b009-110">Remarks</span></span>  
 <span data-ttu-id="6b009-111">若要创建`File`元数据结构，使用[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6b009-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b009-112">要求</span><span class="sxs-lookup"><span data-stu-id="6b009-112">Requirements</span></span>  
 <span data-ttu-id="6b009-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b009-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b009-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b009-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b009-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6b009-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b009-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b009-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b009-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b009-117">See also</span></span>
- [<span data-ttu-id="6b009-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="6b009-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
