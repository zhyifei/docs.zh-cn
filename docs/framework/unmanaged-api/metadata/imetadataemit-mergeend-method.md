---
title: IMetaDataEmit::MergeEnd 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b794a62a0ac0d253f1431be29b43101816dc7233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449437"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd 方法
合并到当前作用域指定一个或多个之前调用的所有元数据作用域[imetadataemit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>参数  
 此方法采用任何参数。  
  
## <a name="remarks"></a>备注  
 此例程会触发实际合并元数据，所有导入以前调用指定作用域`IMetaDataEmit::Merge`，纳入当前输出范围。  
  
 以下特殊情况适用于合并：  
  
-   模块版本标识符 (MVID) 永远不会导入，因为它是唯一的导入作用域中的元数据。  
  
-   没有现有的模块级属性将被覆盖。  
  
     如果模块的属性已设置为当前作用域，导不入任何模块的属性。 但是，如果模块的属性不在当前范围内已设置，它们是导入后仅当它们首次遇到。 如果再次遇到这些模块的属性，它们是重复项。 如果 （MVID 除外） 的所有模块属性的值进行比较，并且没有重复项位于，将引发错误。  
  
-   对于类型定义 (`TypeDef`)，没有重复项将合并到当前作用域。 `TypeDef` 针对每个重复项来检查对象*完全限定对象名称* + *GUID* + *版本号*。 如果没有匹配名称或 GUID，并且任何其他两个元素是不同，将引发错误。 否则为如果所有三个项匹配，`MergeEnd`执行粗略检查以确保这些项确实重复项; 否则，将引发错误。 此粗略检查将查找：  
  
    -   相同的成员声明中的相同顺序出现。 成员标记为`mdPrivateScope`(请参阅[CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md)枚举) 中此检查; 不包括特殊合并。  
  
    -   相同的类布局。  
  
     这意味着，`TypeDef`对象必须始终完全且一致地定义每个元数据范围内声明它; 如果其成员的实现 （为类） 分布在多个编译单元中，假定完整定义为存在于每个范围内，不是增量到每个作用域。 例如，如果与协定相关参数名称，它们必须发出相同的方式到每个作用域;如果它们不是相关的它们不应将发送到元数据。  
  
     例外情况是，`TypeDef`对象可以拥有增量成员标记为`mdPrivateScope`。 在遇到这些`MergeEnd`以增量方式将它们添加到当前范围中不考虑重复项。 因为编译器理解的专用的作用域，因此编译器必须负责强制执行规则。  
  
-   不导入或合并; 相对虚拟地址 (Rva)编译器需要重新发送此信息。  
  
-   自定义特性，仅当合并合并附加到的项。 例如，当第一次遇到类合并与类相关联的自定义属性。 如果与之关联的自定义特性`TypeDef`或`MemberDef`特定于编译单元 （例如成员编译的时间戳），它们将不会合并，并将由编译器删除或更新此类元数据。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
