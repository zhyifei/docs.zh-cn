---
title: ICorDebugModule::IsInMemory 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ae5c16f9f508511e4a15b2eae2c28d68238f1d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415888"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="2e05f-102">ICorDebugModule::IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="2e05f-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="2e05f-103">获取一个值，该值指示仅在内存中是否存在此模块。</span><span class="sxs-lookup"><span data-stu-id="2e05f-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e05f-104">语法</span><span class="sxs-lookup"><span data-stu-id="2e05f-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e05f-105">参数</span><span class="sxs-lookup"><span data-stu-id="2e05f-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="2e05f-106">[out]`true`如果此模块只存在于内存; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="2e05f-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e05f-107">备注</span><span class="sxs-lookup"><span data-stu-id="2e05f-107">Remarks</span></span>  
 <span data-ttu-id="2e05f-108">公共语言运行时 (CLR) 支持原始字节流中的模块加载。</span><span class="sxs-lookup"><span data-stu-id="2e05f-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="2e05f-109">进行此类模块称为*内存中模块*和磁盘上不存在。</span><span class="sxs-lookup"><span data-stu-id="2e05f-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e05f-110">要求</span><span class="sxs-lookup"><span data-stu-id="2e05f-110">Requirements</span></span>  
 <span data-ttu-id="2e05f-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2e05f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e05f-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e05f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e05f-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e05f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e05f-114">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e05f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e05f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e05f-115">See Also</span></span>  
    
 
