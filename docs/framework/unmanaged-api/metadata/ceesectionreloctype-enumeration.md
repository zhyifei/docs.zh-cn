---
title: CeeSectionRelocType 枚举
ms.date: 03/30/2017
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
ms.openlocfilehash: 44a84e0752eecc1c694f3b8cf6e568b72b7d0f5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176209"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 枚举
提供值以影响调用 ICeeGen 时发出的`reloc`指令类型[：：AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
|成员|说明|  
|------------|-----------------|  
|`srRelocAbsolute`|仅生成与节相关的`reloc`，不会将任何内容发送到 .reloc 节。|  
|`srRelocHighLow`|为指针`reloc`大小的位置生成 。 根据平台的不同，这转换为BASED_HIGHLOW或BASED_DIR64。|  
|`srRelocHighAdj`|为`reloc`32 位数字的前 16 位生成 一个，其中底部 16 位包含在 .reloc 表中的下一个单词中。|  
|`srRelocMapToken`|生成令牌映射重新定位，不向 .reloc 部分发送任何内容。|  
|`srRelocRelative`|指示该值是相对地址修复。|  
|`srRelocFilePos`|仅生成与节相关的`reloc`，不会将任何内容发送到 .reloc 节。 这是`reloc`相对于节的文件位置，而不是节的虚拟地址。|  
|`srRelocCodeRelative`|指定与代码相关的地址修复。|  
|`srRelocIA64Imm64`|在`reloc`ia64 指令中为 64`movl`位地址生成 。|  
|`srRelocDir64`|为`reloc`64 位地址生成 。|  
|`srRelocIA64PcRel25`|在`reloc`ia64`br.call`指令中为 25 位 PC 相关地址生成 。|  
|`srRelocIA64PcRel64`|在`reloc`ia64`brl.call`指令中为 64 位 PC 相关地址生成 。|  
|`srRelocAbsoluteTagged`|生成 30 位节相对`reloc`， 用于标记的指针值。|  
|`srRelocSentinel`|一个哨点值，可帮助确保此枚举的任何添加都反映到内部`reloc`名称数组。|  
|`srNoBaseReloc`|指定不发出基`reloc`。|  
|`srRelocPtr`|指示内存的预修复内容是指针而不是节偏移量的值。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
