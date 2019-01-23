---
title: ICorDebugManagedCallback::UpdateModuleSymbols 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b66cc09eda1fe5ea46a55b6239e05b5acec851c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566900"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="22956-102">ICorDebugManagedCallback::UpdateModuleSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="22956-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="22956-103">通知调试器已更改了公共语言运行时模块的符号。</span><span class="sxs-lookup"><span data-stu-id="22956-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22956-104">语法</span><span class="sxs-lookup"><span data-stu-id="22956-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22956-105">参数</span><span class="sxs-lookup"><span data-stu-id="22956-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="22956-106">[in]指向一个 ICorDebugAppDomain 对象，表示包含的模块的符号已发生更改的应用程序域的指针。</span><span class="sxs-lookup"><span data-stu-id="22956-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="22956-107">[in]指向表示的模块的符号已发生更改的 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="22956-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="22956-108">[in]一个指向 Win32 COM`IStream`对象，其中包含已修改的符号。</span><span class="sxs-lookup"><span data-stu-id="22956-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22956-109">备注</span><span class="sxs-lookup"><span data-stu-id="22956-109">Remarks</span></span>  
 <span data-ttu-id="22956-110">此方法提供了通过调用更新模块的符号的调试器的视图的机会[isymunmanagedreader:: Updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)或[isymunmanagedreader:: Replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)。</span><span class="sxs-lookup"><span data-stu-id="22956-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="22956-111">此回调可多次出现相同的模块。</span><span class="sxs-lookup"><span data-stu-id="22956-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="22956-112">调试程序应尝试绑定未绑定的源级别断点。</span><span class="sxs-lookup"><span data-stu-id="22956-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22956-113">要求</span><span class="sxs-lookup"><span data-stu-id="22956-113">Requirements</span></span>  
 <span data-ttu-id="22956-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22956-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22956-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22956-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22956-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22956-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22956-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22956-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22956-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="22956-118">See also</span></span>
- [<span data-ttu-id="22956-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="22956-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
