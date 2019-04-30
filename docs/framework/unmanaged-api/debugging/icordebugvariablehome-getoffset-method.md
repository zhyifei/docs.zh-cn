---
title: ICorDebugVariableHome::GetOffset 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864cb893511bceabd61ce0064065b3866ce01dfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986747"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="804d3-102">ICorDebugVariableHome::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="804d3-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="804d3-103">获取从基寄存器变量的偏移量。</span><span class="sxs-lookup"><span data-stu-id="804d3-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="804d3-104">语法</span><span class="sxs-lookup"><span data-stu-id="804d3-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="804d3-105">参数</span><span class="sxs-lookup"><span data-stu-id="804d3-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="804d3-106">[out]从基寄存器的偏移量。</span><span class="sxs-lookup"><span data-stu-id="804d3-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="804d3-107">返回值</span><span class="sxs-lookup"><span data-stu-id="804d3-107">Return Value</span></span>  
 <span data-ttu-id="804d3-108">此方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="804d3-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="804d3-109">“值”</span><span class="sxs-lookup"><span data-stu-id="804d3-109">Value</span></span>|<span data-ttu-id="804d3-110">描述</span><span class="sxs-lookup"><span data-stu-id="804d3-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="804d3-111">该变量是在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="804d3-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="804d3-112">变量不是在寄存器相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="804d3-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="804d3-113">要求</span><span class="sxs-lookup"><span data-stu-id="804d3-113">Requirements</span></span>  
 <span data-ttu-id="804d3-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="804d3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="804d3-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="804d3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="804d3-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="804d3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="804d3-117">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="804d3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="804d3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="804d3-118">See also</span></span>

- [<span data-ttu-id="804d3-119">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="804d3-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
