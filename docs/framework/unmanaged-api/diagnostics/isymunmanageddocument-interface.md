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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f75e517890275b90523dc42cdac3a83d871beac7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanageddocument-interface"></a>ISymUnmanagedDocument 接口
表示由符号存储引用的文档。 文档由统一资源定位器 (URL) 和 GUID 的文档类型定义。 你可以查找而不考虑如何存储通过使用的 URL 的文档和文档类型 GUID。 你可以在符号存储区中存储的文档源，并通过此接口检索它。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FindClosestLine 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-findclosestline-method.md)|是作为序列点的最近的一行中一行返回此文档中可能也可能不是序列点。|  
|[GetCheckSum 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksum-method.md)|获取校验和。|  
|[GetCheckSumAlgorithmId 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getchecksumalgorithmid-method.md)|获取校验和算法标识符，或如果没有校验和，则返回全为零的 GUID。|  
|[GetDocumentType 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getdocumenttype-method.md)|获取此文档的文档类型。|  
|[GetLanguage 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguage-method.md)|获取此文档的语言标识符。|  
|[GetLanguageVendor 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getlanguagevendor-method.md)|获取此文档的语言供应商。|  
|[GetSourceLength 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcelength-method.md)|获取嵌入源的长度（以字节表示）。|  
|[GetSourceRange 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-getsourcerange-method.md)|返回到给定缓冲区中嵌入源的指定的范围。|  
|[GetURL 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-geturl-method.md)|返回此文档的 URL。|  
|[HasEmbeddedSource 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-hasembeddedsource-method.md)|返回`true`如果该文档具有源嵌入在调试符号; 否则，返回`false`。|  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
