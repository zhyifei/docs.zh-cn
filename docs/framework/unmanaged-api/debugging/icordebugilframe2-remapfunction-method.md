---
title: "ICorDebugILFrame2::RemapFunction 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.RemapFunction
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4def20bc51d1b01b1c05b81a89fc3c983b4d1219
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2remapfunction-method"></a>ICorDebugILFrame2::RemapFunction 方法
通过指定新的 Microsoft 中间语言 (MSIL) 偏移量来重新映射的编辑的函数  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>参数  
 `newILOffset`  
 [in]在放置指令指针的堆栈帧的新 MSIL 偏移量。 此值必须是序列点。  
  
 它是在调用方有责任确保此值的有效性。 例如，MSIL 偏移量不超出边界的函数是否有效。  
  
## <a name="remarks"></a>备注  
 如果已编辑帧的函数，则调试器可以调用`RemapFunction`方法来交换帧的函数的最新版本中，因此可以执行它。 代码执行将在给定的 MSIL 偏移量处开始。  
  
> [!NOTE]
>  调用`RemapFunction`一样调用[icordebugilframe:: Setip](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md)，将立即使失效与生成线程的堆栈跟踪相关的所有调试接口。 这些接口包括[ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)，ICorDebugILFrame、 ICorDebugInternalFrame 和 ICorDebugNativeFrame。  
  
 `RemapFunction`仅在当前帧时，上下文中并且仅在以下情况下，可以调用方法：  
  
-   收到的产品后[icordebugmanagedcallback2:: Functionremapopportunity](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)方面不尚未已持续的回调。  
  
-   由于停止执行代码时[icordebugmanagedcallback:: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)此帧的事件。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
