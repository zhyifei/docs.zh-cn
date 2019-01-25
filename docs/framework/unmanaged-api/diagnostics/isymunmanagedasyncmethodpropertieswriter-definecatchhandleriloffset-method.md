---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55d35db387d6184f68ff31a74253d3d1610c806f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741230"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
设置的 IL 偏移量的编译器生成 catch 处理程序包装异步方法。  
  
 生成 catch 的 IL 偏移量由调试器用于 catch 处理，就好像非用户代码即使它可能会出现在用户代码方法。 具体而言，它用于响应**CatchHandlerFound**异常事件。  
  
## <a name="syntax"></a>语法  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a>返回值  
 返回 `HRESULT`。  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl CorSym.h  
  
## <a name="see-also"></a>请参阅
- [ISymUnmanagedAsyncMethodPropertiesWriter 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
