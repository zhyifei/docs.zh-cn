---
title: ISymUnmanagedReader 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader
helpviewer_keywords:
- ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: aa3cc15d-058e-4e6f-b03e-39569646ba47
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a78616ea1dccdf82c4e00d23d2ff630c98cb4e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431898"
---
# <a name="isymunmanagedreader-interface"></a>ISymUnmanagedReader 接口
表示提供对文档、 方法和符号存储区内的变量的访问的符号读取器。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetDocument 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocument-method.md)|查找文档。|  
|[GetDocuments 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocuments-method.md)|返回在符号存储区中定义的所有文档的数组。|  
|[GetDocumentVersion 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getdocumentversion-method.md)|获取指定的文档的指定的版本。|  
|[GetGlobalVariables 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getglobalvariables-method.md)|返回所有全局变量。|  
|[GetMethod 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethod-method.md)|获取符号读取器方法，给定一个方法标记。|  
|[GetMethodByVersion 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodbyversion-method.md)|获取符号读取器方法，在给定方法标记和编辑复制版本号。|  
|[GetMethodFromDocumentPosition 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodfromdocumentposition-method.md)|返回包含在文档中的给定位置处的断点的方法。|  
|[GetMethodsFromDocumentPosition 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodsfromdocumentposition-method.md)|返回的数组的方法，其中每个包含文档中的给定位置处的断点。|  
|[GetMethodVersion 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getmethodversion-method.md)|获取的方法版本。|  
|[GetNamespaces 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getnamespaces-method.md)|获取在此符号存储区中的全局范围内定义的命名空间。|  
|[GetSymAttribute 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymattribute-method.md)|获取基于其名称的自定义特性。|  
|[GetSymbolStoreFileName 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getsymbolstorefilename-method.md)|提供符号存储区的磁盘上的文件的名称。|  
|[GetUserEntryPoint 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getuserentrypoint-method.md)|如果有，则返回指定为该模块的用户入口点的方法。|  
|[GetVariables 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-getvariables-method.md)|返回一个非本地变量，给定的父级和名称。|  
|[Initialize 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-initialize-method.md)|初始化此读取器将与，以及该模块的文件名称相关联的元数据导入程序接口的符号读取器。|  
|[ReplaceSymbolStore 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)|用增量符号存储区替换现有的符号存储区。|  
|[UpdateSymbolStore 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md)|使用增量符号存储区更新现有的符号存储区。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedReader2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
