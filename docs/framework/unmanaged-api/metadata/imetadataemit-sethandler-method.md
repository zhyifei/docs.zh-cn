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
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003927"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="f1a9a-102">IMetaDataEmit::SetHandler 方法</span><span class="sxs-lookup"><span data-stu-id="f1a9a-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="f1a9a-103">将指定指针所引用的方法设置 `IUnknown` 为标记重新映射的通知回调。</span><span class="sxs-lookup"><span data-stu-id="f1a9a-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a9a-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1a9a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1a9a-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1a9a-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="f1a9a-106">中要注册的处理程序。</span><span class="sxs-lookup"><span data-stu-id="f1a9a-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a9a-107">备注</span><span class="sxs-lookup"><span data-stu-id="f1a9a-107">Remarks</span></span>  
 <span data-ttu-id="f1a9a-108">元数据引擎使用由提供的方法将通知发送 `SetHandler` 到未以优化方式生成记录并且希望优化已保存记录的编译器。</span><span class="sxs-lookup"><span data-stu-id="f1a9a-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="f1a9a-109">如果未通过提供回调方法，则 `SetHandler` 不会对保存执行任何优化，只是在 `IMapToken` 每个作用域的合并上使用合并了若干导入范围。</span><span class="sxs-lookup"><span data-stu-id="f1a9a-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a9a-110">要求</span><span class="sxs-lookup"><span data-stu-id="f1a9a-110">Requirements</span></span>  
 <span data-ttu-id="f1a9a-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a9a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a9a-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="f1a9a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1a9a-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f1a9a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1a9a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1a9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a9a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1a9a-115">See also</span></span>

- [<span data-ttu-id="f1a9a-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="f1a9a-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="f1a9a-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="f1a9a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
