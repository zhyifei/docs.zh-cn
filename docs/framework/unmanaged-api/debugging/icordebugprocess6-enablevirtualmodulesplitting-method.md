---
title: ICorDebugProcess6::EnableVirtualModuleSplitting 方法
ms.date: 03/30/2017
ms.assetid: e7733bd3-68da-47f9-82ef-477db5f2e32d
ms.openlocfilehash: 8ad15d11ce81323b30434b3db98259a74a198f29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178562"
---
# <a name="icordebugprocess6enablevirtualmodulesplitting-method"></a>ICorDebugProcess6::EnableVirtualModuleSplitting 方法
启用或禁用虚拟模块拆分。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnableVirtualModuleSplitting(  
   BOOL enableSplitting  
);  
```  
  
## <a name="parameters"></a>parameters  
 `enableSplitting`  
 `true` 来启用虚拟模块拆分；`false` 来将其禁用。  
  
## <a name="remarks"></a>备注  
 虚拟模块拆分导致[ICorDebug](icordebug-interface.md)识别在生成过程中合并在一起的模块，并将其作为一组单独的模块而不是单个大型模块呈现。 这样做会更改下面描述的各种[ICorDebug](icordebug-interface.md)方法的行为。  
  
> [!NOTE]
> 此方法仅适用于 .NET Native。  
  
 可随时调用方法并更改 `enableSplitting` 值。 它不会在[ICorDebug](icordebug-interface.md)对象中导致任何有状态的功能更改，除了更改[调用虚拟模块拆分和非托管调试 API](#APIs)部分中列出的方法的行为。 调用那些方法时，使用虚拟模块确实会导致性能显著下降。 此外，可能需要大量虚拟化元数据的内存缓存才能正确实现[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) API，即使在关闭虚拟模块拆分后，这些缓存也可能保留。  
  
## <a name="terminology"></a>术语  
 描述虚拟模块拆分时会用到下列术语：  
  
 容器模块，即容器  
 聚合模块。  
  
 子模块，即虚拟模块  
 在容器中发现的各模块。  
  
 普通模块  
 未在生成过程中合并的模块。 它们既不是容器模块也不是子模块。  
  
 但 ICor调试模块接口对象会表示容器模块和子模块。 但是，接口的行为在每种情况下都略有不同，如第>节的\<xref 描述。  
  
## <a name="modules-and-assemblies"></a>模块和程序集  
 在程序集合并的情况下，多模块程序集不受支持，因此模块和程序集之间存在一对一的关系。 每个 ICor调试模块对象（不论其代表容器模块还是子模块）都拥有相应的 ICor调试程序集对象。 [ICorDebugModule：获取组装](icordebugmodule-getassembly-method.md)方法从模块转换为程序集。 要向其他方向映射[，ICorDebugAssembly：：枚举模块](icordebugassembly-enumeratemodules-method.md)方法仅枚举 1 个模块。 因为在此情况下的程序集和模块形成了一个紧密耦合对，术语程序集和模块变得在很大程度上可以互换。  
  
## <a name="behavioral-differences"></a>行为差异  
 容器模块包含以下行为和特征：  
  
- 所有组成子模块的元数据合并在一起。  
  
- 类型名称可能改变。  
  
- [ICorDebugModule：：GetName](icordebugmodule-getname-method.md)方法返回磁盘模块的路径。  
  
- [ICorDebugModule：GetSize](icordebugmodule-getsize-method.md)方法返回该图像的大小。  
  
- ICorDebugAssembly3.EnumerateContainedAssemblies 方法列举子模块。  
  
- ICorDebugAssembly3.GetContainerAssembly 方法返回 `S_FALSE`。  
  
 子模块包含以下行为和特征：  
  
- 他们具有一套减少的元数据，这些元数据只对应合并的原始程序集。  
  
- 元数据名未改变。  
  
- 元数据令牌经生成过程合并之前，不大可能与原始程序集中的令牌匹配。  
  
- [ICorDebugModule：getName](icordebugmodule-getname-method.md)方法返回程序集名称，而不是文件路径。  
  
- [ICorDebugModule：GetSize](icordebugmodule-getsize-method.md)方法返回原始未合并的图像大小。  
  
- ICorDebugModule3.EnumerateContainedAssemblies 方法返回 `S_FALSE`。  
  
- ICorDebugAssembly3.GetContainerAssembly 方法返回包含模块。  
  
## <a name="interfaces-retrieved-from-modules"></a>从模块恢复的接口  
 模块可恢复或创建多个接口。 其中包括：  
  
- ICorDebugClass 对象，由[ICorDebugModule 返回：：获取ClassFromToken](icordebugmodule-getclassfromtoken-method.md)方法。  
  
- ICorDebugAssembly 对象，由[ICorDebugModule：getAssembly](icordebugmodule-getassembly-method.md)方法返回。  
  
 这些对象始终由[ICorDebug](icordebug-interface.md)缓存，无论它们是从容器模块还是子模块创建还是查询它们，它们都将具有相同的指针标识。 子模块提供了这些缓存对象的筛选视图，而非包含各自副本的单独缓存。  
  
<a name="APIs"></a>
## <a name="virtual-module-splitting-and-the-unmanaged-debugging-apis"></a>虚拟模块拆分和未托管调试 API  
 下表显示了虚拟模块拆分如何影响未托管调试 API 中的其他方法的行为。  
  
|方法|`enableSplitting` = `true`|`enableSplitting` = `false`|  
|------------|---------------------------------|----------------------------------|  
|[ICorDebugFunction::GetModule](icordebugfunction-getmodule-method.md)|返回最初定义该功能的子模块|返回该功能合并到的容器模块|  
|[ICorDebugClass::GetModule](icordebugclass-getmodule-method.md)|返回最初定义该类的子模块。|返回该类合并到的容器模块。|  
|ICorDebugModuleDebugEvent::GetModule|返回加载的容器模块。 不管此设置如何，子模块不会收到加载事件。|返回加载的容器模块。|  
|[ICorDebugAppDomain::EnumerateAssemblies](icordebugappdomain-enumerateassemblies-method.md)|返回一组子程序集和普通程序集；不包含容器程序集。 **注：** 如果缺少任何容器程序集，则不会枚举其任何子程序集。 如果任一普通程序集缺少符号，则其可能被枚举或不枚举。|返回一组子程序集和普通程序集；不包含子程序集。 **注：** 如果缺少任何常规程序集，则可能会枚举，也可能不枚举。|  
|[ICorDebug代码：获取代码](icordebugcode-getcode-method.md)（仅参考 IL 代码时）|返回可能在预合并程序集图像中有效的 IL。 具体来说，当包含 IL 的虚拟模块未定义参考类型时，任一内联元数据令牌都可以作为 TypeRef 或 MemberRef 令牌。 这些 TypeRef 或成员Ref 令牌可以在[IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)对象中为相应的虚拟 ICorDebugModule 对象进行备份。|返回预合并程序集图像中的 IL。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorDebugProcess6 接口](icordebugprocess6-interface.md)
- [调试接口](debugging-interfaces.md)
