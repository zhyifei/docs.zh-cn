---
title: "ICorDebugAppDomain::GetModuleFromMetaDataInterface 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetModuleFromMetaDataInterface
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetModuleFromMetaDataInterface
helpviewer_keywords:
- ICorDebugAppDomain::GetModuleFromMetaDatainterface method [.NET Framework debugging]
- GetModuleFromMetaDatainterface method [.NET Framework debugging]
ms.assetid: f35225b3-5dda-4d5a-913d-b3373e9ab81e
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69b1d7d02031e23571a7a5d0e5c64e6bea66d636
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetmodulefrommetadatainterface-method"></a><span data-ttu-id="8ffb2-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface 方法</span><span class="sxs-lookup"><span data-stu-id="8ffb2-102">ICorDebugAppDomain::GetModuleFromMetaDataInterface Method</span></span>
<span data-ttu-id="8ffb2-103">获取对应于给定的元数据接口的模块。</span><span class="sxs-lookup"><span data-stu-id="8ffb2-103">Gets the module that corresponds to the given metadata interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ffb2-104">语法</span><span class="sxs-lookup"><span data-stu-id="8ffb2-104">Syntax</span></span>  
  
```  
HRESULT GetModuleFromMetaDataInterface (  
    [in] IUnknown           *pIMetaData,  
    [out] ICorDebugModule  **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ffb2-105">参数</span><span class="sxs-lookup"><span data-stu-id="8ffb2-105">Parameters</span></span>  
 `pIMetaData`  
 <span data-ttu-id="8ffb2-106">[in]指向一个对象，它之一[元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)。</span><span class="sxs-lookup"><span data-stu-id="8ffb2-106">[in] A pointer to an object that is one of the [Metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
 `ppModule`  
 <span data-ttu-id="8ffb2-107">[out]指向一个到给定的元数据接口表示相对应的模块的 icor 调试模块对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="8ffb2-107">[out] A pointer to the address of an ICorDebugModule object that represents the module corresponding to the given metadata interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ffb2-108">要求</span><span class="sxs-lookup"><span data-stu-id="8ffb2-108">Requirements</span></span>  
 <span data-ttu-id="8ffb2-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8ffb2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ffb2-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ffb2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ffb2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ffb2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ffb2-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ffb2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
