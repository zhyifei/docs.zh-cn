---
title: "ICorDebugModule::GetMetaDataInterface 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetMetaDataInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f4b1944c68db0cbdd8eb49e10433defc953e4494
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="ac9d8-102">ICorDebugModule::GetMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="ac9d8-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="ac9d8-103">获取可用于检查该模块的元数据的元数据接口对象。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9d8-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac9d8-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac9d8-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac9d8-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="ac9d8-106">[in]指定的元数据接口引用 ID。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="ac9d8-107">[out]指向的地址的指针`T:IUnknown`对象之一的[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9d8-108">备注</span><span class="sxs-lookup"><span data-stu-id="ac9d8-108">Remarks</span></span>  
 <span data-ttu-id="ac9d8-109">可以使用调试器`GetMetaDataInterface`方法来执行的模块，它必须这样做才能编辑该模块的原始元数据的副本。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="ac9d8-110">该调试器将调用`GetMetaDataInterface`获取[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口对象模块，然后调用[imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)将模块的元数据的副本保存到内存。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9d8-111">要求</span><span class="sxs-lookup"><span data-stu-id="ac9d8-111">Requirements</span></span>  
 <span data-ttu-id="ac9d8-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac9d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9d8-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac9d8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac9d8-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac9d8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac9d8-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9d8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9d8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac9d8-116">See Also</span></span>  
 [<span data-ttu-id="ac9d8-117">元数据</span><span class="sxs-lookup"><span data-stu-id="ac9d8-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
