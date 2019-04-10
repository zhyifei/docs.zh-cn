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
ms.openlocfilehash: fd0c2da234fa89bbf92c2117d6428d64502da0c5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208171"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="2fa30-102">IMetaDataAssemblyEmit::SetFileProps 方法</span><span class="sxs-lookup"><span data-stu-id="2fa30-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="2fa30-103">修改指定的 `File` 元数据结构。</span><span class="sxs-lookup"><span data-stu-id="2fa30-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa30-104">语法</span><span class="sxs-lookup"><span data-stu-id="2fa30-104">Syntax</span></span>  
  
```  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa30-105">参数</span><span class="sxs-lookup"><span data-stu-id="2fa30-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="2fa30-106">[in]指定的元数据标记`File`要修改的元数据结构。</span><span class="sxs-lookup"><span data-stu-id="2fa30-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="2fa30-107">[in]指向与文件关联的哈希数据的指针。</span><span class="sxs-lookup"><span data-stu-id="2fa30-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="2fa30-108">[in]以字节为单位的大小`pbHashValue`。</span><span class="sxs-lookup"><span data-stu-id="2fa30-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="2fa30-109">[in]按位组合[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)指定文件的各种属性的值。</span><span class="sxs-lookup"><span data-stu-id="2fa30-109">[in] A bitwise combination of [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa30-110">备注</span><span class="sxs-lookup"><span data-stu-id="2fa30-110">Remarks</span></span>  
 <span data-ttu-id="2fa30-111">若要创建`File`元数据结构，使用[imetadataassemblyemit:: Definefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="2fa30-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa30-112">要求</span><span class="sxs-lookup"><span data-stu-id="2fa30-112">Requirements</span></span>  
 <span data-ttu-id="2fa30-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa30-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa30-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2fa30-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fa30-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2fa30-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2fa30-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2fa30-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fa30-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fa30-117">See also</span></span>

- [<span data-ttu-id="2fa30-118">IMetaDataAssemblyEmit 接口</span><span class="sxs-lookup"><span data-stu-id="2fa30-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
