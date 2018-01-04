---
title: "ICorDebugMDA::GetName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c31125b1faf9f14262e8e4a4c6269671a35519f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="85c8d-102">ICorDebugMDA::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="85c8d-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="85c8d-103">获取包含所表示的托管调试助手 (MDA) 的名称的字符串[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="85c8d-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85c8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="85c8d-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85c8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="85c8d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="85c8d-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="85c8d-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="85c8d-107">[out]指向名称的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="85c8d-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="85c8d-108">[out]在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="85c8d-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85c8d-109">备注</span><span class="sxs-lookup"><span data-stu-id="85c8d-109">Remarks</span></span>  
 <span data-ttu-id="85c8d-110">MDA 名称是唯一的值。</span><span class="sxs-lookup"><span data-stu-id="85c8d-110">MDA names are unique values.</span></span> <span data-ttu-id="85c8d-111">`GetName`方法是获取 XML 流并从基于架构的流中提取名称方便性能的方法。</span><span class="sxs-lookup"><span data-stu-id="85c8d-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85c8d-112">惠?</span><span class="sxs-lookup"><span data-stu-id="85c8d-112">Requirements</span></span>  
 <span data-ttu-id="85c8d-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85c8d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85c8d-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85c8d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85c8d-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85c8d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85c8d-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85c8d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85c8d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="85c8d-117">See Also</span></span>  
 [<span data-ttu-id="85c8d-118">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="85c8d-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="85c8d-119">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="85c8d-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
