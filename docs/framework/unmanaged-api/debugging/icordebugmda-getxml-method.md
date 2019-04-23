---
title: ICorDebugMDA::GetXML 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e78b8a2069671d0fe790956ca914225325a78bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228817"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="ab259-102">ICorDebugMDA::GetXML 方法</span><span class="sxs-lookup"><span data-stu-id="ab259-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="ab259-103">获取与由表示托管调试助手 (MDA) 关联的完整 XML 流[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="ab259-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab259-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab259-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab259-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab259-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ab259-106">[in] `szName` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="ab259-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ab259-107">[out]指向 XML 流的长度的指针。</span><span class="sxs-lookup"><span data-stu-id="ab259-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="ab259-108">[out]在其中存储 XML 流的数组。</span><span class="sxs-lookup"><span data-stu-id="ab259-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="ab259-109">该数组可能为空。</span><span class="sxs-lookup"><span data-stu-id="ab259-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab259-110">备注</span><span class="sxs-lookup"><span data-stu-id="ab259-110">Remarks</span></span>  
 <span data-ttu-id="ab259-111">`GetXML`方法可能会影响性能，具体取决于关联的 XML 流的大小。</span><span class="sxs-lookup"><span data-stu-id="ab259-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab259-112">要求</span><span class="sxs-lookup"><span data-stu-id="ab259-112">Requirements</span></span>  
 <span data-ttu-id="ab259-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab259-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab259-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab259-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab259-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab259-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab259-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab259-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab259-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab259-117">See also</span></span>

- [<span data-ttu-id="ab259-118">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="ab259-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="ab259-119">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="ab259-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
