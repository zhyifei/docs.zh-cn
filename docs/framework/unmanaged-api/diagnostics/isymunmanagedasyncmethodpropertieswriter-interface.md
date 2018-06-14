---
title: ISymUnmanagedAsyncMethodPropertiesWriter 接口
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ec66e0064a8d6e8d4664dd8c727aa87621cfd8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427302"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter 接口
允许你定义每个方法符号的可选的异步方法信息。 始终使用与打开的方法;也就是说，对的调用之间[OpenMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)和[CloseMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)。  
  
## <a name="syntax"></a>语法  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>方法  
 此接口包含下列方法：  
  
|方法|描述|  
|------------|-----------------|  
|[DefineAsyncStepInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|定义一组异步等待在当前方法中的操作。<br /><br /> 每个 yield 偏移量与 await 表达式的返回指令，用于标识潜在 yield 相匹配。 每个`breakpointMethod` / `breakpointOffset`对标识异步操作将恢复其中; 它可能在不同的方法。|  
|[DefineCatchHandlerILOffset 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|设置 IL 偏移量的编译器生成 catch 处理程序包装异步方法。<br /><br /> 生成 catch 的 IL 偏移量由调试器用于处理该 catch，就像它是非用户代码，即使它可能会出现在用户代码方法。 具体而言，它用于响应**CatchHandlerFound**异常事件。|  
|[DefineKickoffMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|设置启动异步操作的开始方法。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
