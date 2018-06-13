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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53fd830cdefda58d40f96f8662a80d1888d963dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449194"
---
# <a name="imetadataemitdefinemethod-method"></a>IMetaDataEmit::DefineMethod 方法
创建一个定义为方法或全局函数使用指定的签名，并将令牌返回到该方法定义。  
  
## <a name="syntax"></a>语法  
  
```  
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
  
#### <a name="parameters"></a>参数  
 `td`  
 [in]`mdTypedef`令牌的父类或父接口的方法。 设置`td`到`mdTokenNil`，如果你正在定义的全局函数。  
  
 `szName`  
 [in]Unicode 中的成员名称。  
  
 `dwMethodFlags`  
 [in]值为[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)指定方法或全局函数的特性的枚举。  
  
 `pvSigBlob`  
 [in]方法签名中。 作为提供，并会保持签名。 如果你需要指定任何参数的其他信息，使用[imetadataemit:: Setparamprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)方法。  
  
 `cbSigBlob`  
 [in]中的字节计数`pvSigBlob`。  
  
 `ulCodeRVA`  
 [in]代码的地址。  
  
 `dwImplFlags`  
 [in]值为[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举，指定方法实现功能。  
  
 `pmd`  
 [out]成员标记中。  
  
## <a name="remarks"></a>备注  
 元数据 API 保证为给定的封闭类或接口，在中指定的调用方发出它们按保留相同的顺序中的方法`td`参数。  
  
 有关使用的其他信息`DefineMethod`和特定的参数设置如下所示。  
  
## <a name="slots-in-the-v-table"></a>V-表中的槽  
 运行时使用方法定义来设置 v-表槽。 在一个或多个槽需要已跳过，例如用于这种情况并保留有一个 COM 接口布局，奇偶校验 dummy 方法定义以占用槽或 v-表; 中的槽设置`dwMethodFlags`到`mdRTSpecialName`值[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举和将名称指定为：  
  
 _VtblGap\<*SequenceNumber*>\<\_*槽数*>  
  
 其中*SequenceNumber*是方法的序列号和*槽数*是要跳过 v-表中的槽数。 如果*槽数*是省略，则假定为 1。 这些虚拟方法不是可从托管或非托管代码调用，并从托管或非托管代码中调用它们的任何尝试生成异常。 它们的唯一用途是将会占用空间运行时为 COM 集成生成 v-表中。  
  
## <a name="duplicate-methods"></a>重复的方法  
 不应定义重复的方法。 也就是说，不应调用`DefineMethod`重复的一组值中使用`td`， `wzName`，和`pvSig`参数。 (这三个参数组合在一起唯一定义的方法。)。 但是，可以使用重复三元组，前提是，对于一种方法定义中，你设置`mdPrivateScope`中位`dwMethodFlags`参数。 (`mdPrivateScope`位意味着编译器将发出对此方法定义的引用。)  
  
## <a name="method-implementation-information"></a>方法的实现信息  
 在声明的方法时通常不知道有关方法的实现的信息。 因此，不需要传递中的值`ulCodeRVA`和`dwImplFlags`参数调用时`DefineMethod`。 可以通过更高版本提供值[imetadataemit:: Setmethodimplflags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)或[imetadataemit:: Setrva](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)适当。  
  
 在某些情况下，如平台调用 (PInvoke) 或 COM 互操作方案中，未将提供方法体，和`ulCodeRVA`应设置为零。 在这些情况下，该方法不应被标记为抽象，因为运行时将查找其实现。  
  
## <a name="defining-a-method-for-pinvoke"></a>为 PInvoke 定义方法  
 对于每个要通过 PInvoke 调用的非托管函数，必须定义表示目标的非托管函数的托管的方法。 若要定义的托管的方法，使用`DefineMethod`一些设置为特定值，具体取决于在其中使用 PInvoke 的方法的参数：  
  
-   True PInvoke-涉及驻留在非托管 DLL 的外部的非托管方法的调用。  
  
-   本地 PInvoke — 涉及在当前的托管模块中嵌入的本机非托管方法的调用。  
  
 下表中提供的参数设置。  
  
|参数|值 true PInvoke|本地 PInvoke 值|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||设置`mdStatic`; 清除`mdSynchronized`和`mdAbstract`。|  
|`pvSigBlob`|一个有效的公共语言运行时 (CLR) 方法签名，其参数属于有效的托管类型。|一个有效的 CLR 方法签名，其有效的参数的托管类型。|  
|`ulCodeRVA`||0|  
|`dwImplFlags`|设置`miCil`和`miManaged`。|设置`miNative`和`miUnmanaged`。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
