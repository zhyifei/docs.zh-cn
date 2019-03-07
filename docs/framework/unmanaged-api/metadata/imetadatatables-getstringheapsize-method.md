---
title: IMetaDataTables::GetStringHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a46f7b277987df7e15eb2d534d1bbacc3250f4e1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466006"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="8fb7c-102">IMetaDataTables::GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="8fb7c-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="8fb7c-103">获取以字节为单位的字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fb7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8fb7c-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fb7c-105">参数</span><span class="sxs-lookup"><span data-stu-id="8fb7c-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="8fb7c-106">[out]指向以字节为单位的字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fb7c-107">要求</span><span class="sxs-lookup"><span data-stu-id="8fb7c-107">Requirements</span></span>  
 <span data-ttu-id="8fb7c-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8fb7c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fb7c-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8fb7c-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fb7c-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8fb7c-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fb7c-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fb7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fb7c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fb7c-112">See also</span></span>
- [<span data-ttu-id="8fb7c-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="8fb7c-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8fb7c-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="8fb7c-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
