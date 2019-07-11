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
ms.openlocfilehash: cf6deb4d1420e7b58e1edc7741b683beb591ca5e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782104"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="825db-102">IMetaDataTables::GetUserStringHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="825db-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="825db-103">获取以字节为单位的用户字符串堆的大小。</span><span class="sxs-lookup"><span data-stu-id="825db-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="825db-104">语法</span><span class="sxs-lookup"><span data-stu-id="825db-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="825db-105">参数</span><span class="sxs-lookup"><span data-stu-id="825db-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="825db-106">[out]指向以字节为单位的用户字符串堆的大小的指针。</span><span class="sxs-lookup"><span data-stu-id="825db-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="825db-107">要求</span><span class="sxs-lookup"><span data-stu-id="825db-107">Requirements</span></span>  
 <span data-ttu-id="825db-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="825db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="825db-109">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="825db-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="825db-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="825db-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="825db-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="825db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="825db-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="825db-112">See also</span></span>

- [<span data-ttu-id="825db-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="825db-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="825db-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="825db-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
