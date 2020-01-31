---
title: ICorDebugLoadedModule::GetBaseAddress 方法
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788444"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="9f31d-102">ICorDebugLoadedModule::GetBaseAddress 方法</span><span class="sxs-lookup"><span data-stu-id="9f31d-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="9f31d-103">获取已加载模块的基址。</span><span class="sxs-lookup"><span data-stu-id="9f31d-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f31d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f31d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f31d-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f31d-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="9f31d-106">[out] 指向已加载模块的基址的指针。</span><span class="sxs-lookup"><span data-stu-id="9f31d-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f31d-107">备注</span><span class="sxs-lookup"><span data-stu-id="9f31d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9f31d-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9f31d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f31d-109">需求</span><span class="sxs-lookup"><span data-stu-id="9f31d-109">Requirements</span></span>  
 <span data-ttu-id="9f31d-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f31d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f31d-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f31d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f31d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f31d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f31d-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f31d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f31d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f31d-114">See also</span></span>

- [<span data-ttu-id="9f31d-115">ICorDebugLoadedModule 接口</span><span class="sxs-lookup"><span data-stu-id="9f31d-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="9f31d-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="9f31d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
