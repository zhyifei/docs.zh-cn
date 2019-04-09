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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac0e5db4a87b49d631bad4411f03fae8c1199aea
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125627"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="72034-102">IMetaDataEmit::SetHandler 方法</span><span class="sxs-lookup"><span data-stu-id="72034-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="72034-103">设置由指定引用的方法`IUnknown`指针作为标记重新映射的通知回调。</span><span class="sxs-lookup"><span data-stu-id="72034-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72034-104">语法</span><span class="sxs-lookup"><span data-stu-id="72034-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72034-105">参数</span><span class="sxs-lookup"><span data-stu-id="72034-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="72034-106">[in]要注册的处理程序。</span><span class="sxs-lookup"><span data-stu-id="72034-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72034-107">备注</span><span class="sxs-lookup"><span data-stu-id="72034-107">Remarks</span></span>  
 <span data-ttu-id="72034-108">元数据引擎使用的提供的方法来发送通知`SetHandler`，到编译器不优化方式生成记录并希望保存的记录进行优化。</span><span class="sxs-lookup"><span data-stu-id="72034-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="72034-109">如果不通过提供的回调方法`SetHandler`，将执行未优化上保存除若干导入作用域已合并使用`IMapToken`上每个作用域合并。</span><span class="sxs-lookup"><span data-stu-id="72034-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72034-110">要求</span><span class="sxs-lookup"><span data-stu-id="72034-110">Requirements</span></span>  
 <span data-ttu-id="72034-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="72034-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72034-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="72034-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72034-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="72034-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="72034-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="72034-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="72034-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="72034-115">See also</span></span>

- [<span data-ttu-id="72034-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="72034-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="72034-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="72034-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
