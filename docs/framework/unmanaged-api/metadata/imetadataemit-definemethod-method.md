---
title: IMetaDataEmit::DefineMethod 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177662"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod 方法
使用指定签名的方法或全局函数创建定义，并将令牌返回到该方法定义。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT DefineMethod (
    [in]  mdTypeDef         td,
    [in]  LPCWSTR           szName,
    [in]  DWORD             dwMethodFlags,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [in]  ULONG             ulCodeRVA,
    [in]  DWORD             dwImplFlags,
    [out] mdMethodDef      *pmd  
);  
```  
  
## <a name="parameters"></a>parameters  
 `td`  
 [在]方法`mdTypedef`的父类或父接口的令牌。 如果要`td`定义`mdTokenNil`全局函数，则设置为 ，设置为 。。  
  
 `szName`  
 [在]Unicode 中的成员名称。  
  
 `dwMethodFlags`  
 [在][CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举的值，用于指定方法或全局函数的属性。  
  
 `pvSigBlob`  
 [在]方法签名。 签名将保留为提供。 如果需要为任何参数指定其他信息，请使用[IMetaDataEmit：：setParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)方法。  
  
 `cbSigBlob`  
 [在]中的`pvSigBlob`字节计数。  
  
 `ulCodeRVA`  
 [在]代码的地址。  
  
 `dwImplFlags`  
 [在][CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举的值，用于指定方法的实现特征。  
  
 `pmd`  
 [出]成员令牌。  
  
## <a name="remarks"></a>备注  
 元数据 API 保证以与调用方为给定的封闭类或接口发出方法的顺序保留方法，该类或接口在`td`参数中指定。  
  
 有关 使用`DefineMethod`和特定参数设置的其他信息，请参阅下文。  
  
## <a name="slots-in-the-v-table"></a>V 表中的插槽  
 运行时使用方法定义来设置 v 表槽。 如果需要跳过一个或多个插槽（例如，使用 COM 接口布局保留奇偶校验），则定义虚拟方法以占用 v 表中的插槽或插槽;例如，使用 COM 接口布局保留奇偶校验，则使用虚拟方法占用 v-table 中的插槽或插槽。将`dwMethodFlags`设置为`mdRTSpecialName`[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举的值，并将名称指定为：  
  
 _VtblGap\<*序数*>\<*CountOfSlots*计数\_>
  
 *其中序列编号*是方法的序列号 *，CountOfSlots*是 v 表中要跳过的插槽数。 如果省略*了 CountOflots，* 则假定为 1。 这些虚拟方法不能从托管或非托管代码调用，任何尝试调用它们（从托管代码或非托管代码）都会生成异常。 它们的唯一目的是占用运行时为 COM 集成生成的 v 表中的空间。  
  
## <a name="duplicate-methods"></a>重复方法  
 不应定义重复的方法。 `DefineMethod`也就是说，不应使用`td`中`wzName`重复的值集调用 ， 和`pvSig`参数。 （这三个参数一起唯一地定义方法。 但是，可以使用重复的三重，前提是，对于方法定义之一，可以在`mdPrivateScope``dwMethodFlags`参数中设置位。 （该`mdPrivateScope`位表示编译器不会发出对此方法定义的引用。  
  
## <a name="method-implementation-information"></a>方法实现信息  
 在声明方法时，通常不知道有关方法实现的信息。 因此，调用 时不需要传递`ulCodeRVA`和`dwImplFlags`参数中的值。 `DefineMethod` 这些值稍后可以通过[IMetaDataEmit：：设置方法Implflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)或[IMetaDataEmit：：SetRVA，](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)视情况而定。  
  
 在某些情况下，如平台调用 （PInvoke） 或 COM 互通方案，将不会提供方法正文，并且`ulCodeRVA`应设置为零。 在这些情况下，方法不应标记为抽象，因为运行时将定位实现。  
  
## <a name="defining-a-method-for-pinvoke"></a>定义 PInvoke 的方法  
 要通过 PInvoke 调用每个非托管函数，必须定义表示目标非托管函数的托管方法。 要定义托管方法，请使用`DefineMethod`设置为特定值的某些参数，具体取决于 PInvoke 的使用方式：  
  
- True PInvoke - 涉及调用驻留在非托管 DLL 中的外部非托管方法。  
  
- 本地 PInvoke - 涉及调用嵌入在当前托管模块中的本机非托管方法。  
  
 参数设置在下表中给出。  
  
|参数|真实 PInvoke 的值|本地 PInvoke 的值|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||设置`mdStatic`;清楚`mdSynchronized`和`mdAbstract`。|  
|`pvSigBlob`|有效的通用语言运行时 （CLR） 方法签名，具有有效的托管类型的参数。|具有有效托管类型的参数的有效 CLR 方法签名。|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|设置 `miCil` 和 `miManaged`。|设置 `miNative` 和 `miUnmanaged`。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
