---
title: IMetaDataTables::GetBlobHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
ms.openlocfilehash: c32407c3fc0bc5a045b80ec48937699826d981af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177167"
---
# <a name="imetadatatablesgetblobheapsize-method"></a><span data-ttu-id="7fcfc-102">IMetaDataTables::GetBlobHeapSize 方法</span><span class="sxs-lookup"><span data-stu-id="7fcfc-102">IMetaDataTables::GetBlobHeapSize Method</span></span>
<span data-ttu-id="7fcfc-103">获取二进制大型对象 （BLOB） 堆的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="7fcfc-103">Gets the size, in bytes, of the binary large object (BLOB) heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fcfc-104">语法</span><span class="sxs-lookup"><span data-stu-id="7fcfc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="7fcfc-105">parameters</span><span class="sxs-lookup"><span data-stu-id="7fcfc-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="7fcfc-106">[出]指向 BLOB 堆的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="7fcfc-106">[out] A pointer to the size, in bytes, of the BLOB heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fcfc-107">要求</span><span class="sxs-lookup"><span data-stu-id="7fcfc-107">Requirements</span></span>  
 <span data-ttu-id="7fcfc-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7fcfc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fcfc-109">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="7fcfc-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7fcfc-110">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7fcfc-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7fcfc-111">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fcfc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fcfc-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fcfc-112">See also</span></span>

- [<span data-ttu-id="7fcfc-113">IMetaDataTables 接口</span><span class="sxs-lookup"><span data-stu-id="7fcfc-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="7fcfc-114">IMetaDataTables2 接口</span><span class="sxs-lookup"><span data-stu-id="7fcfc-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
