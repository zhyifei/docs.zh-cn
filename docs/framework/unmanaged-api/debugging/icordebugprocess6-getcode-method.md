---
title: ICorDebugProcess6::GetCode 方法
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948637"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="d3e1e-102">ICorDebugProcess6::GetCode 方法</span><span class="sxs-lookup"><span data-stu-id="d3e1e-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="d3e1e-103">获取特定代码地址上的托管代码的相关信息。</span><span class="sxs-lookup"><span data-stu-id="d3e1e-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e1e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d3e1e-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3e1e-105">参数</span><span class="sxs-lookup"><span data-stu-id="d3e1e-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="d3e1e-106">[in]一个[CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md)值，该值指定托管的代码段的起始地址。</span><span class="sxs-lookup"><span data-stu-id="d3e1e-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="d3e1e-107">[out]指向表示托管代码段"ICorDebugCode"对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d3e1e-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3e1e-108">备注</span><span class="sxs-lookup"><span data-stu-id="d3e1e-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d3e1e-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d3e1e-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3e1e-110">要求</span><span class="sxs-lookup"><span data-stu-id="d3e1e-110">Requirements</span></span>  
 <span data-ttu-id="d3e1e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3e1e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3e1e-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3e1e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3e1e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3e1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3e1e-114">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e1e-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e1e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3e1e-115">See also</span></span>

- [<span data-ttu-id="d3e1e-116">ICorDebugProcess6 接口</span><span class="sxs-lookup"><span data-stu-id="d3e1e-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="d3e1e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="d3e1e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
