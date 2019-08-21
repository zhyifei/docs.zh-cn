---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: e0493ed3f8796019d5715ef468c88675b9970a39
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973837"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a>ICorProfilerInfo9:: GetCodeInfo4 方法
  
 给定本机代码起始地址, 返回存储此代码的虚拟内存块。
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```  
  
#### <a name="parameters"></a>参数  
 `pNativeCodeStartAddress`  
 中指向本机函数开头的指针。  

 `cCodeInfos`  
 [in] `codeInfos` 数组的大小。  
  
 `pcCodeInfos`  
 弄指向可用[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构总数的指针。  
  
 `codeInfos`  
 [out] 调用方提供的缓冲区。 返回此方法后，它包含一个 `COR_PRF_CODE_INFO` 结构数组，每个结构描述一个本机代码块。  
  
## <a name="remarks"></a>备注  
 方法类似于 [GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md), 只不过它可以查找方法的不同本机版本的代码信息。 `GetCodeInfo4`  
  
> [!NOTE]
>  `GetCodeInfo4`可以触发垃圾回收。
  
 范围按公共中间语言 (CIL) 偏移递增的顺序进行排序。  
  
 返回`GetCodeInfo4`后, 必须验证`codeInfos`缓冲区是否足够大以包含所有[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构。 为此，请将 `cCodeInfos` 的值和 `cchName` 参数的值进行比较。 如果`cCodeInfos`除以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) `codeInfos` `cCodeInfos`结构的大小小于`GetCodeInfo4` , 则分配更大的缓冲区, 用新的、更大的大小更新, 然后再次调用。 `pcCodeInfos`  
  
 或者，可以先用长度为零的 `codeInfos` 缓冲区调用 `GetCodeInfo4` 以获取正确的缓冲区大小。 然后`codeInfos` , 可以将缓冲区大小设置为中`pcCodeInfos`返回的值, 再乘以[COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)结构的大小, 然后再次调用`GetCodeInfo4` 。   
  

## <a name="requirements"></a>要求  
 **适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。  
  
 **标头：** Corprof.idl, Corprof.idl  
  
 **类库**CorGuids.lib  
  
 **.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>请参阅
- [ICorProfilerInfo9 接口](../../../../docs/framework/unmanaged-api/profiling/ICorProfilerInfo9-interface.md)

