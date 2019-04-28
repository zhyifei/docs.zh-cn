---
title: ICorDebugAppDomain::IsAttached 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996159"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="71722-102">ICorDebugAppDomain::IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="71722-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="71722-103">获取一个值，该值指示是否将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="71722-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71722-104">语法</span><span class="sxs-lookup"><span data-stu-id="71722-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71722-105">参数</span><span class="sxs-lookup"><span data-stu-id="71722-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="71722-106">[out]`true`调试程序附加到应用程序域; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="71722-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71722-107">备注</span><span class="sxs-lookup"><span data-stu-id="71722-107">Remarks</span></span>  
 <span data-ttu-id="71722-108">不能使用 ICorDebugController 方法，直到将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="71722-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71722-109">要求</span><span class="sxs-lookup"><span data-stu-id="71722-109">Requirements</span></span>  
 <span data-ttu-id="71722-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71722-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71722-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="71722-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="71722-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71722-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71722-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71722-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
