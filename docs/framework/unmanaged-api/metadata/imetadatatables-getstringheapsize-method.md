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
ms.openlocfilehash: 7f6f16ebe57be0d09e97fe8aa95df892c2b02394
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696251"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="322b7-102">IMetaDataTables::GetStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="322b7-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="322b7-103">获取以字节为单位的字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="322b7-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="322b7-104">语法</span><span class="sxs-lookup"><span data-stu-id="322b7-104">Syntax</span></span>  
  
```  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="322b7-105">参数</span><span class="sxs-lookup"><span data-stu-id="322b7-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="322b7-106">[out]指向以字节为单位的字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="322b7-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="322b7-107">要求</span><span class="sxs-lookup"><span data-stu-id="322b7-107">Requirements</span></span>  
 <span data-ttu-id="322b7-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="322b7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="322b7-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="322b7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="322b7-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="322b7-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="322b7-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="322b7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322b7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="322b7-112">See also</span></span>
- [<span data-ttu-id="322b7-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="322b7-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="322b7-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="322b7-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
