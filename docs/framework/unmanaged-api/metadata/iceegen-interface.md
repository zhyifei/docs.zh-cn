---
title: ICeeGen 接口
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: ae3c372951de00b097d0a8437039a3a85bf3aabf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426149"
---
# <a name="iceegen-interface"></a>ICeeGen 接口
提供用于动态代码编译的方法。  
  
 This interface is obsolete and should not be used.  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[AddSectionReloc 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-addsectionreloc-method.md)|已过时。 Adds a .reloc instruction to the code base.|  
|[AllocateMethodBuffer 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-allocatemethodbuffer-method.md)|已过时。 Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.|  
|[ComputePointer 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-computepointer-method.md)|已过时。 Determines the buffer for the specified code section.|  
|[EmitString 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-emitstring-method.md)|已过时。 Emits the specified string into the code base.|  
|[GenerateCeeFile 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceefile-method.md)|已过时。 Generates a code-base file that contains the code base currently loaded into this `ICeeGen`.|  
|[GenerateCeeMemoryImage 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-generateceememoryimage-method.md)|已过时。 Generates an image in memory for the code base.|  
|[GetIlSection 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getilsection-method.md)|已过时。 Gets the section of the intermediate language code base referenced by the specified handle.|  
|[GetIMapTokenIface 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getimaptokeniface-method.md)|已过时。 Gets the interface referenced by the specified token.|  
|[GetMethodBuffer 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getmethodbuffer-method.md)|已过时。 Gets a buffer of the appropriate size for the method at the specified relative virtual address.|  
|[GetSectionBlock 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectionblock-method.md)|已过时。 Gets a section block of the code base.|  
|[GetSectionCreate 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectioncreate-method.md)|已过时。 Generates and gets a code section using the specified name and flag values.|  
|[GetSectionDataLen 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getsectiondatalen-method.md)|已过时。 Gets the length of the specified section.|  
|[GetString 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstring-method.md)|已过时。 Gets the string stored at the specified relative virtual address.|  
|[GetStringSection 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-getstringsection-method.md)|已过时。 Gets a string representation of the code section referenced by the specified handle.|  
|[TruncateSection 方法](../../../../docs/framework/unmanaged-api/metadata/iceegen-truncatesection-method.md)|已过时。 Truncates the specified code section by the specified length.|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **Header:** Cor.h  
  
 **Library:** Used as a resource in MsCorEE.dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
