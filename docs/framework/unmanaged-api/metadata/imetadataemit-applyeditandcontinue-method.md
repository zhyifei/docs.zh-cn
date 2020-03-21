---
title: IMetaDataEmit::ApplyEditAndContinue 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.ApplyEditAndContinue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::ApplyEditAndContinue
helpviewer_keywords:
- ApplyEditAndContinue method [.NET Framework metadata]
- IMetaDataEmit::ApplyEditAndContinue method [.NET Framework metadata]
ms.assetid: 35991289-f389-495d-8caa-a6384fb1d557
topic_type:
- apiref
ms.openlocfilehash: f876187624d066b9e672fbf44a984d6d02a54c43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175871"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="b28f3-102">IMetaDataEmit::ApplyEditAndContinue 方法</span><span class="sxs-lookup"><span data-stu-id="b28f3-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="b28f3-103">使用在指定的元数据中所做的更改更新当前程序集范围。</span><span class="sxs-lookup"><span data-stu-id="b28f3-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b28f3-104">语法</span><span class="sxs-lookup"><span data-stu-id="b28f3-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b28f3-105">parameters</span><span class="sxs-lookup"><span data-stu-id="b28f3-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="b28f3-106">\[在\]指向[IUnknown](/cpp/atl/iunknown)对象的指针中，该对象表示来自可移植可执行文件 （PE） 文件中的增量元数据。</span><span class="sxs-lookup"><span data-stu-id="b28f3-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="b28f3-107">增量元数据是元数据块，包括对模块实际元数据副本所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b28f3-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b28f3-108">要求</span><span class="sxs-lookup"><span data-stu-id="b28f3-108">Requirements</span></span>  
 <span data-ttu-id="b28f3-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b28f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b28f3-110">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="b28f3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b28f3-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b28f3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b28f3-112">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b28f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b28f3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b28f3-113">See also</span></span>

- [<span data-ttu-id="b28f3-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="b28f3-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b28f3-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="b28f3-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
