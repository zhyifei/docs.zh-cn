---
title: IMetaDataTables::GetGuidHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuidHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuidHeapSize
helpviewer_keywords:
- GetGuidHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetGuidHeapSize method [.NET Framework metadata]
ms.assetid: e875cbee-1ad9-4f1a-bf03-38cdb8ff371a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97d196769b549022ce498958fc34cf08df442d0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="a5350-102">IMetaDataTables::GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="a5350-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="a5350-103">获取用字节表示，GUID 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="a5350-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5350-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5350-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5350-105">参数</span><span class="sxs-lookup"><span data-stu-id="a5350-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="a5350-106">[out]指向以字节为单位，GUID 堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="a5350-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5350-107">要求</span><span class="sxs-lookup"><span data-stu-id="a5350-107">Requirements</span></span>  
 <span data-ttu-id="a5350-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5350-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5350-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5350-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5350-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a5350-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5350-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5350-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5350-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5350-112">See Also</span></span>  
 [<span data-ttu-id="a5350-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="a5350-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="a5350-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="a5350-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
