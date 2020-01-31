---
title: ICorDebugNativeFrame::GetRegisterSet 方法
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: affab7ae99dbdf85e7eadc89bfd24c42408626ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792822"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="b2c18-102">ICorDebugNativeFrame::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="b2c18-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="b2c18-103">获取此堆栈帧的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="b2c18-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c18-104">语法</span><span class="sxs-lookup"><span data-stu-id="b2c18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2c18-105">参数</span><span class="sxs-lookup"><span data-stu-id="b2c18-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="b2c18-106">弄一个指向[ICorDebugRegisterSet](icordebugregisterset-interface.md)对象地址的指针，该对象表示此堆栈帧的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="b2c18-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2c18-107">需求</span><span class="sxs-lookup"><span data-stu-id="b2c18-107">Requirements</span></span>  
 <span data-ttu-id="b2c18-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b2c18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c18-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2c18-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2c18-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2c18-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2c18-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c18-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2c18-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2c18-112">See also</span></span>
