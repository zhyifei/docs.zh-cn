---
title: "IEnumDefinitionIdentity 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumDefinitionIdentity
helpviewer_keywords: IEnumDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: 8263e75d-251b-4abc-8a1a-c62884142232
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79e2a35a455407715a05e826d31c5d5ab05a02ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ienumdefinitionidentity-interface"></a>IEnumDefinitionIdentity 接口
用作的集合的枚举数`IDefinitionIdentity`对象。  
  
## <a name="syntax"></a>语法  
  
```  
IEnumDefinitionIdentity : IUnknown {  
  
    HRESULT Clone (  
        [out] IEnumDefinitionIdentity **ppIEnumDefinitionIdentity  
    );  
  
    HRESULT Next (  
        [in]  ULONG               celt,  
        [out, length_is(celt), size_is(*pceltWritten)]  
              IDefinitionIdentity *rgpIDefinitionIdentity[],  
        [out] ULONG               *pceltWritten  
    );  
  
    HRESULT Reset ();  
  
    HRESULT Skip (  
        [in] ULONG celt  
    );  
  
};  
```  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|`IEnumDefinitionIdentity::Clone`|到新获取的接口指针`IEnumDefinitionIdentity`对象，其中包含与此相同的成员`IEnumDefinitionIdentity`。|  
|`IEnumDefinitionIdentity::Next`|获取指定的数目的`IDefinitionIdentity`对象，从当前位置开始。|  
|`IEnumDefinitionIdentity::Reset`|将指令指针移到此开头`IEnumDefinitionIdentity`。|  
|`IEnumDefinitionIdentity::Skip`|将指令指针向前移动指定数量的元素，从当前位置开始。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Isolation.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [合成接口](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [IDefinitionIdentity 接口](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
