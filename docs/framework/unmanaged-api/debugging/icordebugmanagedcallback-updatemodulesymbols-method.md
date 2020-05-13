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
ms.openlocfilehash: 9ee6f43c94b8ff2e765d2a0dde0697c4c895a94f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212368"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="4393d-102">ICorDebugManagedCallback::UpdateModuleSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="4393d-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="4393d-103">通知调试器公共语言运行时模块的符号已发生更改。</span><span class="sxs-lookup"><span data-stu-id="4393d-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4393d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4393d-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4393d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4393d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="4393d-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含已更改符号的模块的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4393d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="4393d-107">中指向 ICorDebugModule 对象的指针，该对象表示符号已更改的模块。</span><span class="sxs-lookup"><span data-stu-id="4393d-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="4393d-108">中指向 Win32 COM `IStream` 对象的指针，该对象包含修改后的符号。</span><span class="sxs-lookup"><span data-stu-id="4393d-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4393d-109">备注</span><span class="sxs-lookup"><span data-stu-id="4393d-109">Remarks</span></span>  
 <span data-ttu-id="4393d-110">此方法通过调用[ISymUnmanagedReader：： UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)或[ISymUnmanagedReader：： ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md)，提供更新模块的符号的调试器视图的机会。</span><span class="sxs-lookup"><span data-stu-id="4393d-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="4393d-111">对于同一个模块，此回调可能发生多次。</span><span class="sxs-lookup"><span data-stu-id="4393d-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="4393d-112">调试器应尝试绑定未绑定的源级断点。</span><span class="sxs-lookup"><span data-stu-id="4393d-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4393d-113">要求</span><span class="sxs-lookup"><span data-stu-id="4393d-113">Requirements</span></span>  
 <span data-ttu-id="4393d-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4393d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4393d-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4393d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4393d-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4393d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4393d-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4393d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4393d-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4393d-118">See also</span></span>

- [<span data-ttu-id="4393d-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="4393d-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
