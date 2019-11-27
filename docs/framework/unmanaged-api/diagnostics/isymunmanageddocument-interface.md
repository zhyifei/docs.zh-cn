---
title: ISymUnmanagedDocument 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument
helpviewer_keywords:
- ISymUnmanagedDocument interface [.NET Framework debugging]
ms.assetid: 5c26b366-6e81-467c-9dd0-02dd26fee0a3
topic_type:
- apiref
ms.openlocfilehash: 3fa7b6b19d81e374cdb09b07ec181a7f4249a5eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449104"
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument 接口
表示由符号存储引用的文档。 文档由统一资源定位器（URL）和文档类型 GUID 定义。 可以通过使用 URL 和文档类型 GUID 来查找文档，而不考虑其存储方式。 可以将文档源存储在符号存储区中，并通过此接口进行检索。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[FindClosestLine 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|如果此文档中的一行可能是也可能不是序列点，则返回作为序列点的最近行。|  
|[GetCheckSum 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|获取校验和。|  
|[GetCheckSumAlgorithmId 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|如果没有校验和，则获取校验和算法标识符，或返回所有零的 GUID。|  
|[GetDocumentType 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|获取此文档的文档类型。|  
|[GetLanguage 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|获取此文档的语言标识符。|  
|[GetLanguageVendor 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|获取此文档的语言供应商。|  
|[GetSourceLength 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|获取嵌入源的长度（以字节表示）。|  
|[GetSourceRange 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|将嵌入源的指定范围返回到给定缓冲区中。|  
|[GetURL 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|返回此文档的 URL。|  
|[HasEmbeddedSource 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|如果文档在调试符号中嵌入了源，则返回 `true`;否则，将返回 `false`。|  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
