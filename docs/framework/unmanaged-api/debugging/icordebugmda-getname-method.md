---
title: ICorDebugMDA::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
ms.openlocfilehash: 522ac2fd448abaaba48d4d5c20551e8029b35fd4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793229"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="98290-102">ICorDebugMDA::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="98290-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="98290-103">获取一个字符串，该字符串包含由[ICorDebugMDA](icordebugmda-interface.md)表示的托管调试助手（MDA）的名称。</span><span class="sxs-lookup"><span data-stu-id="98290-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98290-104">语法</span><span class="sxs-lookup"><span data-stu-id="98290-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98290-105">参数</span><span class="sxs-lookup"><span data-stu-id="98290-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="98290-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="98290-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="98290-107">弄指向名称长度的指针。</span><span class="sxs-lookup"><span data-stu-id="98290-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="98290-108">弄要在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="98290-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98290-109">备注</span><span class="sxs-lookup"><span data-stu-id="98290-109">Remarks</span></span>  
 <span data-ttu-id="98290-110">MDA 名称是唯一值。</span><span class="sxs-lookup"><span data-stu-id="98290-110">MDA names are unique values.</span></span> <span data-ttu-id="98290-111">`GetName` 方法可方便地获取 XML 流，并根据架构从流中提取名称。</span><span class="sxs-lookup"><span data-stu-id="98290-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98290-112">需求</span><span class="sxs-lookup"><span data-stu-id="98290-112">Requirements</span></span>  
 <span data-ttu-id="98290-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98290-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98290-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98290-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98290-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98290-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98290-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98290-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98290-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98290-117">See also</span></span>

- [<span data-ttu-id="98290-118">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="98290-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="98290-119">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="98290-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
