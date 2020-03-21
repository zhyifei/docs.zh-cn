---
title: IMetaDataEmit::SetHandler 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177544"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="5c54e-102">IMetaDataEmit::SetHandler 方法</span><span class="sxs-lookup"><span data-stu-id="5c54e-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="5c54e-103">将指定`IUnknown`指针引用的方法集为令牌重映射的通知回调。</span><span class="sxs-lookup"><span data-stu-id="5c54e-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c54e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5c54e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c54e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5c54e-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="5c54e-106">[在]要注册的处理程序。</span><span class="sxs-lookup"><span data-stu-id="5c54e-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c54e-107">备注</span><span class="sxs-lookup"><span data-stu-id="5c54e-107">Remarks</span></span>  
 <span data-ttu-id="5c54e-108">元数据引擎使用 提供`SetHandler`的方法向未以优化方式生成记录并希望优化保存的记录的编译器发送通知。</span><span class="sxs-lookup"><span data-stu-id="5c54e-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="5c54e-109">如果未通过`SetHandler`提供回调方法，则不会对保存执行优化，除非每个作用域在合并`IMapToken`时合并了多个导入作用域。</span><span class="sxs-lookup"><span data-stu-id="5c54e-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c54e-110">要求</span><span class="sxs-lookup"><span data-stu-id="5c54e-110">Requirements</span></span>  
 <span data-ttu-id="5c54e-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5c54e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c54e-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5c54e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c54e-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5c54e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c54e-114">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c54e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c54e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5c54e-115">See also</span></span>

- [<span data-ttu-id="5c54e-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5c54e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5c54e-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5c54e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
