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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c15c554e0ec135b33d671a83b5e27d0a2a89b731
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444251"
---
# <a name="imetadataemitapplyeditandcontinue-method"></a><span data-ttu-id="d3c21-102">IMetaDataEmit::ApplyEditAndContinue 方法</span><span class="sxs-lookup"><span data-stu-id="d3c21-102">IMetaDataEmit::ApplyEditAndContinue Method</span></span>
<span data-ttu-id="d3c21-103">使用指定的元数据中所做的更改更新当前程序集作用域。</span><span class="sxs-lookup"><span data-stu-id="d3c21-103">Updates the current assembly scope with the changes made in the specified metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c21-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3c21-104">Syntax</span></span>  
  
```  
HRESULT ApplyEditAndContinue (   
    [in]  IUnknown    *pImport  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d3c21-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3c21-105">Parameters</span></span>  
 `pImport`  
 <span data-ttu-id="d3c21-106">[in]指向 <<!--zzxref:IUnknown --> `IUnknown`> 从可移植可执行 (PE) 文件表示的增量元数据的对象。</span><span class="sxs-lookup"><span data-stu-id="d3c21-106">[in] Pointer to an <<!--zzxref:IUnknown --> `IUnknown`> object that represents the delta metadata from the portable executable (PE) file.</span></span>  
  
 <span data-ttu-id="d3c21-107">增量元数据是元数据，它包含对模块的实际元数据的副本所做的更改的块。</span><span class="sxs-lookup"><span data-stu-id="d3c21-107">The delta metadata is the block of metadata that includes the changes that were made to the copy of the module's actual metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3c21-108">要求</span><span class="sxs-lookup"><span data-stu-id="d3c21-108">Requirements</span></span>  
 <span data-ttu-id="d3c21-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3c21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c21-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d3c21-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3c21-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="d3c21-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3c21-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c21-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3c21-113">See Also</span></span>  
 [<span data-ttu-id="d3c21-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="d3c21-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="d3c21-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="d3c21-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
