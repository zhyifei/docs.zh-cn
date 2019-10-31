---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130375"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 方法

返回一个枚举器，该枚举器指向给定的 NGen 模块中定义的所有方法，并内联给定方法。

## <a name="syntax"></a>语法

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a>参数

`inlinersModuleId`\
中NGen 模块的标识符。

`inlineeModuleId`\
中定义 `inlineeMethodId`的模块的标识符。 有关详细信息，请参阅备注部分。

`inlineeMethodId`\
中内联方法的标识符。 有关详细信息，请参阅备注部分。

`incompleteData`\
弄指示 `ppEnum` 是否包含内联给定方法的所有方法的标志。  有关详细信息，请参阅备注部分。

`ppEnum`\
弄指向枚举器地址的指针

## <a name="remarks"></a>备注

`inlineeModuleId` 和 `inlineeMethodId` 一起构成了可能内联的方法的完整标识符。 例如，假设 module `A` 定义方法 `Simple.Add`：

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

和模块 B 定义 `Fancy.AddTwice`：

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

还假定 `Fancy.AddTwice` inlines 调用 `SimpleAdd`。 探查器可以使用此枚举器来查找模块 B 中定义的内联 `Simple.Add`的所有方法，结果将枚举 `AddTwice`。  `inlineeModuleId` 是模块 `A`的标识符，`inlineeMethodId` 是 `Simple.Add(int a, int b)`的标识符。

如果在函数返回后 `incompleteData` 为 true，则枚举器不包含内联给定方法的所有方法。 如果尚未加载 inliners 模块的一个或多个直接或间接依赖项，则可能会发生这种情况。 如果探查器需要准确的数据，则应在加载更多模块时重试，最好是在每个模块加载时重试。

`EnumNgenModuleMethodsInliningThisMethod` 方法可用于解决 ReJIT 的内联限制。 ReJIT 使探查器可以更改方法的实现，然后动态为其创建新代码。 例如，我们可以按如下所示更改 `Simple.Add`：

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

但是，因为 `Fancy.AddTwice` 已经内联 `Simple.Add`，它将继续与之前一样具有相同的行为。 若要解决此限制，调用方必须搜索内联 `Simple.Add` 的所有模块中的所有方法，并对这些方法使用 `ICorProfilerInfo5::RequestRejit`。 重新编译这些方法时，它们将具有 `Simple.Add` 的新行为，而不是旧的行为。

## <a name="requirements"></a>要求

**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。

**头文件：** CorProf.idl、CorProf.h

**库：** CorGuids.lib

**.NET Framework 版本：** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]

## <a name="see-also"></a>请参阅

- [ICorProfilerInfo6 接口](icorprofilerinfo6-interface.md)
