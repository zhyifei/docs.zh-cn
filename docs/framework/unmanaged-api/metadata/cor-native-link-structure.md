---
title: COR_NATIVE_LINK 结构
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007970"
---
# <a name="cor_native_link-structure"></a>COR_NATIVE_LINK 结构
包含用于链接本机代码的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`m_linkType`|要在本机代码中链接的类型。 此值为[CorNativeLinkType](cornativelinktype-enumeration.md)值之一。|  
|`m_flags`|链接本机代码时链接器使用的标志。 此值为[CorNativeLinkFlags](cornativelinkflags-enumeration.md)值之一。|  
|`m_entryPoint`|表示入口点的 MemberRef 元数据标记。 格式为 `lib:entrypoint`。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据结构](metadata-structures.md)
- [CorNativeLinkType 枚举](cornativelinktype-enumeration.md)
- [CorNativeLinkFlags 枚举](cornativelinkflags-enumeration.md)
