---
title: "IMetaDataTables::GetStringHeapSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetStringHeapSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f7ff6d6296e36d8d1a55682b453941b932bd590
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="2dffd-102">IMetaDataTables::GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="2dffd-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="2dffd-103">获取用字节表示，字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="2dffd-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="2dffd-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2dffd-105">参数</span><span class="sxs-lookup"><span data-stu-id="2dffd-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="2dffd-106">[out]指向以字节为单位，在字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="2dffd-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dffd-107">惠?</span><span class="sxs-lookup"><span data-stu-id="2dffd-107">Requirements</span></span>  
 <span data-ttu-id="2dffd-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2dffd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dffd-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2dffd-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2dffd-110">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="2dffd-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2dffd-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dffd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dffd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dffd-112">See Also</span></span>  
 [<span data-ttu-id="2dffd-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="2dffd-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="2dffd-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="2dffd-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
