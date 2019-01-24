---
title: ICorDebugMDA::GetDescription 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74b9ef2cdd48c403eb5a50d357a673eee3102106
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54548231"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="87b94-102">ICorDebugMDA::GetDescription 方法</span><span class="sxs-lookup"><span data-stu-id="87b94-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="87b94-103">获取一个字符串，该字符串包含由表示托管调试助手 (MDA) 的说明[ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="87b94-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87b94-104">语法</span><span class="sxs-lookup"><span data-stu-id="87b94-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87b94-105">参数</span><span class="sxs-lookup"><span data-stu-id="87b94-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="87b94-106">[in]将存储说明的字符串缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="87b94-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="87b94-107">[out]指向字符串缓冲区中返回的字节数的指针。</span><span class="sxs-lookup"><span data-stu-id="87b94-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="87b94-108">[out]包含此 MDA 的说明的字符串缓冲区。</span><span class="sxs-lookup"><span data-stu-id="87b94-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87b94-109">备注</span><span class="sxs-lookup"><span data-stu-id="87b94-109">Remarks</span></span>  
 <span data-ttu-id="87b94-110">字符串可以是长度为零。</span><span class="sxs-lookup"><span data-stu-id="87b94-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b94-111">要求</span><span class="sxs-lookup"><span data-stu-id="87b94-111">Requirements</span></span>  
 <span data-ttu-id="87b94-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="87b94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87b94-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87b94-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87b94-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87b94-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b94-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b94-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="87b94-116">See also</span></span>
- [<span data-ttu-id="87b94-117">ICorDebugMDA 接口</span><span class="sxs-lookup"><span data-stu-id="87b94-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="87b94-118">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="87b94-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
