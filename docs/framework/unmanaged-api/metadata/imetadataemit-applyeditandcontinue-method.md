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
ms.openlocfilehash: 7ce9ac95c7183a7d47c367914d80f77c57dde0d7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005760"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="702e3-102">IMetaDataEmit::ApplyEditAndContinue 方法</span><span class="sxs-lookup"><span data-stu-id="702e3-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="702e3-103">用在指定的元数据中进行的更改更新当前程序集范围。</span><span class="sxs-lookup"><span data-stu-id="702e3-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="702e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="702e3-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyEditAndContinue (
    [in]  IUnknown    *pImport  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="702e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="702e3-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="702e3-106">\[\]指向一个[IUnknown](/cpp/atl/iunknown)对象的指针，该对象表示来自可移植可执行（PE）文件的增量元数据。</span><span class="sxs-lookup"><span data-stu-id="702e3-106">\[in\] Pointer to an [IUnknown](/cpp/atl/iunknown) object that represents the delta metadata from the portable executable (PE) file.</span></span>
  
 <span data-ttu-id="702e3-107">增量元数据是元数据的块，其中包括对模块的实际元数据副本所做的更改。</span><span class="sxs-lookup"><span data-stu-id="702e3-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="702e3-108">要求</span><span class="sxs-lookup"><span data-stu-id="702e3-108">Requirements</span></span>  
 <span data-ttu-id="702e3-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="702e3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="702e3-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="702e3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="702e3-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="702e3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="702e3-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="702e3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="702e3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="702e3-113">See also</span></span>

- [<span data-ttu-id="702e3-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="702e3-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="702e3-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="702e3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
