---
title: IMetaDataEmit::SetMethodProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 534afdd5990435c6b4db5ef8ea27a8065b199496
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050007"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="f7d31-102">IMetaDataEmit::SetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="f7d31-102">IMetaDataEmit::SetMethodProps Method</span></span>
<span data-ttu-id="f7d31-103">设置或更新存储在指定的相对虚拟地址，通过调用之前定义的方法的功能[imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d31-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d31-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7d31-104">Syntax</span></span>  
  
```  
HRESULT SetMethodProps (   
    [in]  mdMethodDef md,   
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,   
    [in]  DWORD       dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d31-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7d31-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="f7d31-106">[in]若要更改方法的标记。</span><span class="sxs-lookup"><span data-stu-id="f7d31-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="f7d31-107">[in]成员属性。</span><span class="sxs-lookup"><span data-stu-id="f7d31-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="f7d31-108">[in]代码的地址。</span><span class="sxs-lookup"><span data-stu-id="f7d31-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="f7d31-109">[in]该方法实现标志。</span><span class="sxs-lookup"><span data-stu-id="f7d31-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d31-110">要求</span><span class="sxs-lookup"><span data-stu-id="f7d31-110">Requirements</span></span>  
 <span data-ttu-id="f7d31-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7d31-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d31-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7d31-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7d31-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f7d31-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d31-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d31-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d31-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7d31-115">See also</span></span>

- [<span data-ttu-id="f7d31-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f7d31-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f7d31-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f7d31-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
