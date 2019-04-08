---
title: ICorDebugModule::GetMetaDataInterface 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37710fbb7acc50b80d7acebe4194b019c0b64660
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102591"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="d5126-102">ICorDebugModule::GetMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="d5126-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="d5126-103">获取可用于检查该模块的元数据的元数据接口对象。</span><span class="sxs-lookup"><span data-stu-id="d5126-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5126-104">语法</span><span class="sxs-lookup"><span data-stu-id="d5126-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5126-105">参数</span><span class="sxs-lookup"><span data-stu-id="d5126-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="d5126-106">[in]指定的元数据接口引用 ID。</span><span class="sxs-lookup"><span data-stu-id="d5126-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="d5126-107">[out]指向的地址的指针`T:IUnknown`对象，它是之一[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="d5126-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5126-108">备注</span><span class="sxs-lookup"><span data-stu-id="d5126-108">Remarks</span></span>  
 <span data-ttu-id="d5126-109">可以使用调试器`GetMetaDataInterface`方法对于模块，它必须以编辑该模块来执行此操作的原始元数据的副本。</span><span class="sxs-lookup"><span data-stu-id="d5126-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="d5126-110">该调试器将调用`GetMetaDataInterface`若要获取[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口对象对于模块，然后调用[imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)将模块的元数据的副本保存到内存。</span><span class="sxs-lookup"><span data-stu-id="d5126-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5126-111">要求</span><span class="sxs-lookup"><span data-stu-id="d5126-111">Requirements</span></span>  
 <span data-ttu-id="d5126-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5126-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5126-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5126-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5126-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5126-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d5126-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d5126-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5126-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5126-116">See also</span></span>

- [<span data-ttu-id="d5126-117">元数据</span><span class="sxs-lookup"><span data-stu-id="d5126-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
