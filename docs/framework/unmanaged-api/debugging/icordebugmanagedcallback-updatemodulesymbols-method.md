---
title: "ICorDebugManagedCallback::UpdateModuleSymbols 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.UpdateModuleSymbols
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a1606c256bbfd3b0a7de29b84aace1b4831a016
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="2b611-102">ICorDebugManagedCallback::UpdateModuleSymbols 方法</span><span class="sxs-lookup"><span data-stu-id="2b611-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="2b611-103">通知调试器已更改了公共语言运行时模块的符号。</span><span class="sxs-lookup"><span data-stu-id="2b611-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b611-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b611-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b611-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b611-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="2b611-106">[in]指向一个表示包含在其中更改符号的模块的应用程序域的 ICorDebugAppDomain 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2b611-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="2b611-107">[in]指向一个表示已在其中更改符号的模块的 icor 调试模块对象的指针。</span><span class="sxs-lookup"><span data-stu-id="2b611-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="2b611-108">[in]一个指向 Win32 COM`IStream`对象，其中包含已修改的符号。</span><span class="sxs-lookup"><span data-stu-id="2b611-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b611-109">备注</span><span class="sxs-lookup"><span data-stu-id="2b611-109">Remarks</span></span>  
 <span data-ttu-id="2b611-110">此方法提供了一个机会更新模块的符号的调试器的视图，通过调用[isymunmanagedreader:: Updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)或[isymunmanagedreader:: Replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2b611-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="2b611-111">此回调可以对同一模块中发生多次。</span><span class="sxs-lookup"><span data-stu-id="2b611-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="2b611-112">调试器应尝试将绑定未绑定的源级的断点。</span><span class="sxs-lookup"><span data-stu-id="2b611-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b611-113">要求</span><span class="sxs-lookup"><span data-stu-id="2b611-113">Requirements</span></span>  
 <span data-ttu-id="2b611-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b611-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b611-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b611-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b611-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b611-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b611-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b611-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b611-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b611-118">See Also</span></span>  
 [<span data-ttu-id="2b611-119">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="2b611-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
