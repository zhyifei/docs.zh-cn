---
title: IMetaDataEmit::SaveToMemory 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bc840df9dd0793a7347b7f0d8a05296a09d634c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192103"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="de641-102">IMetaDataEmit::SaveToMemory 方法</span><span class="sxs-lookup"><span data-stu-id="de641-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="de641-103">将保存到指定的内存区域的当前作用域中的所有元数据。</span><span class="sxs-lookup"><span data-stu-id="de641-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de641-104">语法</span><span class="sxs-lookup"><span data-stu-id="de641-104">Syntax</span></span>  
  
```  
HRESULT SaveToMemory (   
    [out]  void        *pbData,   
    [in]   ULONG       cbData   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de641-105">参数</span><span class="sxs-lookup"><span data-stu-id="de641-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="de641-106">[out]要开始编写元数据地址。</span><span class="sxs-lookup"><span data-stu-id="de641-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="de641-107">[in]以字节为单位分配的内存大小。</span><span class="sxs-lookup"><span data-stu-id="de641-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de641-108">要求</span><span class="sxs-lookup"><span data-stu-id="de641-108">Requirements</span></span>  
 <span data-ttu-id="de641-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de641-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de641-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="de641-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de641-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="de641-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="de641-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="de641-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de641-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="de641-113">See also</span></span>

- [<span data-ttu-id="de641-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="de641-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="de641-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="de641-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
