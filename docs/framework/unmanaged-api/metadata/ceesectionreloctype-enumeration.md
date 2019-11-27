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
ms.openlocfilehash: efce0c13944b383c42cbff6a6af4795293ee2989
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444153"
---
# <a name="ceesectionreloctype-enumeration"></a>CeeSectionRelocType 枚举
提供一些值，以影响在对[ICeeGen：： AddSectionReloc](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)的调用中发出的 `reloc` 指令的类型。  
  
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
  
## <a name="members"></a>Members  
  
|成员|说明|  
|------------|-----------------|  
|`srRelocAbsolute`|仅生成与节相关的 `reloc`，不向 .reloc 节发送任何内容。|  
|`srRelocHighLow`|为指针大小的位置生成 `reloc`。 这会根据平台转换为 BASED_HIGHLOW 或 BASED_DIR64。|  
|`srRelocHighAdj`|为32位数字的前16位生成 `reloc`，其中，后16位包含在 .reloc 表的下一个单词中。|  
|`srRelocMapToken`|生成一个标记映射重定位，无需将其发送到 .reloc 部分。|  
|`srRelocRelative`|指示值是相对地址链接地址。|  
|`srRelocFilePos`|仅生成与节相关的 `reloc`，不向 .reloc 节发送任何内容。 此 `reloc` 相对于该节的文件位置，而不是该部分的虚拟地址。|  
|`srRelocCodeRelative`|指定代码相对地址链接地址。|  
|`srRelocIA64Imm64`|为 ia64 `movl` 指令中的64位地址生成 `reloc`。|  
|`srRelocDir64`|为64位地址生成 `reloc`。|  
|`srRelocIA64PcRel25`|为 ia64 `br.call` 指令中的25位 PC 相对地址生成 `reloc`。|  
|`srRelocIA64PcRel64`|为 ia64 `brl.call` 指令中的64位 PC 相对地址生成 `reloc`。|  
|`srRelocAbsoluteTagged`|生成一个与标记指针值相对应的30位相对 `reloc`。|  
|`srRelocSentinel`|一个 sentinel 值，用于帮助确保对此枚举的任何添加都反映到内部 `reloc` 名称数组中。|  
|`srNoBaseReloc`|指定不发出基 `reloc`。|  
|`srRelocPtr`|一个值，该值指示内存的修正内容是指针而不是节偏移量。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
- [AddSectionReloc 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)
