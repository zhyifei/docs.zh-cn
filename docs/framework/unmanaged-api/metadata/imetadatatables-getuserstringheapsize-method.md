---
title: IMetaDataTables::GetUserStringHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1215da0816c1fc7cdfaee0da167118909f8e5eb3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466097"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="d9dc7-102">IMetaDataTables::GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="d9dc7-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="d9dc7-103">获取以字节为单位的用户字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="d9dc7-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9dc7-104">语法</span><span class="sxs-lookup"><span data-stu-id="d9dc7-104">Syntax</span></span>  
  
```  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9dc7-105">参数</span><span class="sxs-lookup"><span data-stu-id="d9dc7-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="d9dc7-106">[out]指向以字节为单位的用户字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="d9dc7-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9dc7-107">要求</span><span class="sxs-lookup"><span data-stu-id="d9dc7-107">Requirements</span></span>  
 <span data-ttu-id="d9dc7-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d9dc7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9dc7-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9dc7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9dc7-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d9dc7-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9dc7-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9dc7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9dc7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9dc7-112">See also</span></span>
- [<span data-ttu-id="d9dc7-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="d9dc7-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d9dc7-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="d9dc7-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
