---
title: "ICeeGen::AddSectionReloc 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.AddSectionReloc
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a74f01e3904c6f3f472110288abbec42fa892fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenaddsectionreloc-method"></a>ICeeGen::AddSectionReloc 方法
将.reloc 指令添加到基本代码。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `section`  
 [in]内存中要向其中添加.reloc 指令的代码的部分。  
  
 `offset`  
 [in]部分的偏移量。  
  
 `relativeTo`  
 [in]向其部分`offset`引用。  
  
 `relocType`  
 [in]之一[CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md)值，指示.reloc 指令，若要添加的类型。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [ICeeGen 接口](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
