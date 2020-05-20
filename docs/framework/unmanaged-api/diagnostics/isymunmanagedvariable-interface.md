---
title: ISymUnmanagedVariable 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610166"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable 接口
表示变量，如参数、局部变量或字段。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetAddressField1 方法](isymunmanagedvariable-getaddressfield1-method.md)|获取此变量的第一个地址字段。 其含义取决于地址的类型。|  
|[GetAddressField2 方法](isymunmanagedvariable-getaddressfield2-method.md)|获取此变量的第二个地址字段。 其含义取决于地址的类型。|  
|[GetAddressField3 方法](isymunmanagedvariable-getaddressfield3-method.md)|获取此变量的第三个地址字段。 其含义取决于地址的类型。|  
|[GetAddressKind 方法](isymunmanagedvariable-getaddresskind-method.md)|获取此变量的地址类型。|  
|[GetAttributes 方法](isymunmanagedvariable-getattributes-method.md)|获取此变量的特性标志。|  
|[GetEndOffset 方法](isymunmanagedvariable-getendoffset-method.md)|获取此变量在其父级内的结束偏移量。|  
|[GetName 方法](isymunmanagedvariable-getname-method.md)|获取此变量的名称。|  
|[GetSignature 方法](isymunmanagedvariable-getsignature-method.md)|获取此变量的签名。|  
|[GetStartOffset 方法](isymunmanagedvariable-getstartoffset-method.md)|获取此变量在其父级内的起始偏移量。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](diagnostics-symbol-store-interfaces.md)
