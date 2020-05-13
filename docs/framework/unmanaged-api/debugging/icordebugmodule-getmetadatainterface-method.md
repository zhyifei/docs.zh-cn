---
title: ICorDebugModule::GetMetaDataInterface 方法
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
ms.openlocfilehash: 8f3cc16054d4b5340c9460e9c3fbcba6e563567a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212550"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a>ICorDebugModule::GetMetaDataInterface 方法
获取可用于检查模块的元数据的元数据接口对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a>参数  
 `riid`  
 中用于指定元数据接口的引用 ID。  
  
 `ppObj`  
 弄指向对象地址的指针，该 `T:IUnknown` 对象是一个[元数据接口](../metadata/metadata-interfaces.md)。  
  
## <a name="remarks"></a>备注  
 调试器可以使用 `GetMetaDataInterface` 方法创建模块的原始元数据的副本，必须执行此操作才能编辑该模块。 调试器调用 `GetMetaDataInterface` 以获取该模块的[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)接口对象，然后调用[IMetaDataEmit：： SaveToMemory](../metadata/imetadataemit-savetomemory-method.md)将模块的元数据副本保存到内存。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据](../metadata/index.md)
