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
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213668"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="8dc3a-102">ICorDebugMDA::GetName 方法</span><span class="sxs-lookup"><span data-stu-id="8dc3a-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="8dc3a-103">获取一个字符串，该字符串包含由[ICorDebugMDA](icordebugmda-interface.md)表示的托管调试助手（MDA）的名称。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dc3a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8dc3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dc3a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8dc3a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8dc3a-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8dc3a-107">弄指向名称长度的指针。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="8dc3a-108">弄要在其中存储名称的数组。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dc3a-109">备注</span><span class="sxs-lookup"><span data-stu-id="8dc3a-109">Remarks</span></span>  
 <span data-ttu-id="8dc3a-110">MDA 名称是唯一值。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-110">MDA names are unique values.</span></span> <span data-ttu-id="8dc3a-111">`GetName`方法是获取 XML 流并基于该架构从流中提取名称的一种方便的性能方法。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dc3a-112">要求</span><span class="sxs-lookup"><span data-stu-id="8dc3a-112">Requirements</span></span>  
 <span data-ttu-id="8dc3a-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc3a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dc3a-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8dc3a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8dc3a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8dc3a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8dc3a-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8dc3a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dc3a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dc3a-117">See also</span></span>

- [<span data-ttu-id="8dc3a-118">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="8dc3a-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="8dc3a-119">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="8dc3a-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
