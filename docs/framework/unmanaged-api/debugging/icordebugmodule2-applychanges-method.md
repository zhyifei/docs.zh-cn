---
title: ICorDebugModule2::ApplyChanges 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a406e945a67352bc7f126b40bd56f4a11dd693b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges 方法
适用于正在运行的进程中元数据的更改和 Microsoft 中间语言 (MSIL) 代码中的更改。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cbMetadata`  
 [in]大小 （以字节为单位的增量元数据）。  
  
 `pbMetadata`  
 [in]包含增量元数据的缓冲区。 缓冲区的地址返回从[imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)方法。  
  
 元数据中的相对虚拟地址 (Rva) 应为相对于 MSIL 代码开头。  
  
 `cbIL`  
 [in]大小 （以字节为单位的增量 MSIL 代码）。  
  
 `pbIL`  
 [in]包含更新的 MSIL 代码的缓冲区。  
  
## <a name="remarks"></a>备注  
 `pbMetadata`参数是特殊的增量元数据格式 (通过为输出[imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md))。 `pbMetadata` 将以前的元数据为基础，并描述每个更改将应用于该基类。  
  
 与此相反， `pbIL[`] 参数包含更新的方法的新 MSIL，而且旨在完全替换该方法的以前 MSIL  
  
 当已在调试器的内存中创建的增量 MSIL 和元数据时，调试器将调用`ApplyChanges`发送到公共语言运行时 (CLR) 所做的更改。 运行时会更新其元数据的表，将新的 MSIL 放入此过程中，并设置新的 MSIL 中实时 (JIT) 编译。 应用所做的更改后，应调用调试器[imetadataemit2:: Resetenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)准备的下一步的编辑会话。 然后，调试器可能继续执行过程。  
  
 每当调试器调用`ApplyChanges`对具有增量元数据的模块，它还应调用[imetadataemit:: Applyeditandcontinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)与所有除外复制该模块的元数据的副本上相同的增量元数据用于发出所做的更改。 如果元数据的副本以某种方式变得扩展同步与实际的元数据，调试器始终丢弃该副本，也可以获取的新副本。  
  
 如果`ApplyChanges`方法失败，则调试会话处于无效状态，必须重新启动。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
