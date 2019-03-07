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
ms.openlocfilehash: f0b41c03f5e6e08144ae566a3543d352c168555f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472104"
---
# <a name="imetadatatablesgetguidheapsize-method"></a><span data-ttu-id="17f93-102">IMetaDataTables::GetGuidHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="17f93-102">IMetaDataTables::GetGuidHeapSize Method</span></span>
<span data-ttu-id="17f93-103">获取以字节为单位，GUID 堆的大小。</span><span class="sxs-lookup"><span data-stu-id="17f93-103">Gets the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17f93-104">语法</span><span class="sxs-lookup"><span data-stu-id="17f93-104">Syntax</span></span>  
  
```  
HRESULT GetGuidHeapSize (  
    [out] ULONG   *pcbGuids  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17f93-105">参数</span><span class="sxs-lookup"><span data-stu-id="17f93-105">Parameters</span></span>  
 `pcbGuids`  
 <span data-ttu-id="17f93-106">[out]指向的大小，以字节为单位，GUID 堆的指针。</span><span class="sxs-lookup"><span data-stu-id="17f93-106">[out] A pointer to the size, in bytes, of the GUID heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17f93-107">要求</span><span class="sxs-lookup"><span data-stu-id="17f93-107">Requirements</span></span>  
 <span data-ttu-id="17f93-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17f93-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17f93-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="17f93-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17f93-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="17f93-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17f93-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17f93-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f93-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="17f93-112">See also</span></span>
- [<span data-ttu-id="17f93-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="17f93-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="17f93-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="17f93-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
