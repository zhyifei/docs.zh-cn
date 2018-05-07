---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
[在.NET Framework 4.6 和更高版本中受支持]  
  
 返回到给定的 NGen 模块和内联给定方法中定义的所有方法的枚举。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `inlinersModuleId`  
 [in]NGen 模块的标识符。  
  
 `inlineeModuleId`  
 [in]定义模块的标识符`inlineeMethodId`。 有关详细信息，请参阅备注部分。  
  
 `inlineeMethodId`  
 [in]内联方法的标识符。 有关详细信息，请参阅备注部分。  
  
 `incompleteData`  
 [out]一个标志，指示是否`ppEnum`包含给定的方法的所有内联的方法。  有关详细信息，请参阅备注部分。  
  
 `ppEnum`  
 [out]枚举器的地址指针  
  
## <a name="remarks"></a>备注  
 `inlineeModuleId` 和`inlineeMethodId`一起构成了可能是内联的方法的完整标识符。 例如，假定模块`A`定义的方法`Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 和模块 Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 允许还假定`Fancy.AddTwice`内联调用到`SimpleAdd`。 探查器可以使用此枚举器查找模块 B 中哪些以内联方式定义的所有方法`Simple.Add`，结果将枚举和`AddTwice`。  `inlineeModuleId` 是模块的标识符`A`，和`inlineeeMethodId`是标识符`Simple.Add(int a, int b)`。  
  
 如果`incompleteData`true 后该函数返回时，枚举数不包含内联的所有方法的给定的方法。 这可能会在一个或多直接或间接依赖关系的内联模块尚未尚未加载。 如果探查器需要准确的数据，它应稍后重试更多模块加载后，最好是在每个模块加载。  
  
 `EnumNgenModuleMethodsInliningThisMethod`方法可以用于解决上的限制为 ReJIT 内联。 ReJIT 允许探查器更改方法的实现，然后动态为它创建新的代码。 例如，我们无法更改`Simple.Add`，如下所示：  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 但是因为`Fancy.AddTwice`具有已内联`Simple.Add`，它将继续像以前那样具有相同的行为。 若要解决这种限制，调用方具有在其中进行搜索的所有方法的所有模块中内联`Simple.Add`并用`ICorProfilerInfo5::RequestRejit`上的每个这些方法。 重新编译方法时，它们将具有新的行为`Simple.Add`而不是这一旧行为。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorProfilerInfo6 接口](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
