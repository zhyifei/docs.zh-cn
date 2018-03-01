---
title: "IMetaDataEmit::SetHandler 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ccb35c12e1d9c2fade9d8760d0a2e39807c92de9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="901c9-102">IMetaDataEmit::SetHandler 方法</span><span class="sxs-lookup"><span data-stu-id="901c9-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="901c9-103">设置指定所引用的方法`IUnknown`指针作为令牌重新映射通知回调。</span><span class="sxs-lookup"><span data-stu-id="901c9-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="901c9-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="901c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="901c9-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="901c9-106">[in]要注册的处理程序。</span><span class="sxs-lookup"><span data-stu-id="901c9-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="901c9-107">备注</span><span class="sxs-lookup"><span data-stu-id="901c9-107">Remarks</span></span>  
 <span data-ttu-id="901c9-108">元数据引擎通过使用提供的方法来发送通知`SetHandler`，到编译器不以优化方式生成记录并希望保存的记录进行优化。</span><span class="sxs-lookup"><span data-stu-id="901c9-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="901c9-109">如果不通过提供的回调方法`SetHandler`，将执行不进行优化上保存除若干导入作用域已合并使用`IMapToken`上每个作用域的合并。</span><span class="sxs-lookup"><span data-stu-id="901c9-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901c9-110">惠?</span><span class="sxs-lookup"><span data-stu-id="901c9-110">Requirements</span></span>  
 <span data-ttu-id="901c9-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="901c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901c9-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="901c9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="901c9-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="901c9-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="901c9-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="901c9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="901c9-115">See Also</span></span>  
 [<span data-ttu-id="901c9-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="901c9-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="901c9-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="901c9-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
