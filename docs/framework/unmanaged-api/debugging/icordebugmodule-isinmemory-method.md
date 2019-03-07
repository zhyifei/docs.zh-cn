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
ms.openlocfilehash: 0f057896d9dd65a850c0b07e4084bc263e804d20
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497361"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="ed7aa-102">ICorDebugModule::IsInMemory 方法</span><span class="sxs-lookup"><span data-stu-id="ed7aa-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="ed7aa-103">获取一个值，指示仅在内存中是否存在此模块。</span><span class="sxs-lookup"><span data-stu-id="ed7aa-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed7aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed7aa-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed7aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed7aa-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="ed7aa-106">[out]`true`如果此模块只存在于内存; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ed7aa-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed7aa-107">备注</span><span class="sxs-lookup"><span data-stu-id="ed7aa-107">Remarks</span></span>  
 <span data-ttu-id="ed7aa-108">公共语言运行时 (CLR) 支持原始字节流中的模块的加载。</span><span class="sxs-lookup"><span data-stu-id="ed7aa-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="ed7aa-109">进行此类模块称为*内存中模块*和磁盘上不存在。</span><span class="sxs-lookup"><span data-stu-id="ed7aa-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed7aa-110">要求</span><span class="sxs-lookup"><span data-stu-id="ed7aa-110">Requirements</span></span>  
 <span data-ttu-id="ed7aa-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed7aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed7aa-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed7aa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed7aa-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed7aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed7aa-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed7aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed7aa-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed7aa-115">See also</span></span>


