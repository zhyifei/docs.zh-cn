---
title: "CeeSectionRelocType 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d257778a9a05e2654d7f91c0205424d001f5ae3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 枚举
提供值来影响的一种`reloc`指令发出对的调用中[iceegen:: Addsectionreloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,       
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`srRelocAbsolute`|生成仅部分相对`reloc`、 发送到.reloc 节执行任何操作。|  
|`srRelocHighLow`|生成`reloc`指针大小的位置。 这将转换为 BASED_HIGHLOW 或 BASED_DIR64 因平台而异。|  
|`srRelocHighAdj`|生成`reloc`前几位的 32 位数字，其中.reloc 表中的下一个单词中包含的底部 16 位的 16 位。|  
|`srRelocMapToken`|生成令牌映射重定位，发送到.reloc 节执行任何操作。|  
|`srRelocRelative`|指示的值是相对地址修正。|  
|`srRelocFilePos`|生成仅部分相对`reloc`、 发送到.reloc 节执行任何操作。 这`reloc`是相对于文件位置的部分中，该节的虚拟地址。|  
|`srRelocCodeRelative`|指定代码相对地址修正。|  
|`srRelocIA64Imm64`|生成`reloc`ia64 中的 64 位地址`movl`指令。|  
|`srRelocDir64`|生成`reloc`针对 64 位地址。|  
|`srRelocIA64PcRel25`|生成`reloc`ia64 中的 25 位 PC 相对地址`br.call`指令。|  
|`srRelocIA64PcRel64`|生成`reloc`ia64 中的 64 位 PC 相对地址`brl.call`指令。|  
|`srRelocAbsoluteTagged`|生成 30 位的部分相对`reloc`，用于标记的指针值。|  
|`srRelocSentinel`|要帮助确保任何添加到此枚举的一个 sentinel 值反映到内部`reloc`名称数组。|  
|`srNoBaseReloc`|指定不发出基类`reloc`。|  
|`srRelocPtr`|一个值，该值的内存的前修正内容一个指针，而不是部分偏移量。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)  
 [AddSectionReloc 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
