---
title: "ISymUnmanagedBinder2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedBinder2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedBinder2 Interface
helpviewer_keywords: ISymUnmanagedBinder2 interface [.NET Framework debugging]
ms.assetid: 7a59f405-73e8-4434-8bcc-a9dc45ea08e6
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0fff140f6848b91e811ef4546a3e8fd50eb61e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedbinder2-interface"></a>ISymUnmanagedBinder2 接口
表示非托管代码的符号联编程序和扩展[ISymUnmanagedBinder](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)接口。  
  
> [!IMPORTANT]
>  它是从受信任的源中打开程序数据库 (PDB) 文件会带来安全风险。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetReaderForFile2 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-getreaderforfile2-method.md)|指定元数据接口和文件名称，则会返回正确 <<!--zz xref:ISymUnmanagedReader --> `ISymUnmanagedReader`> 将读取与模块关联的调试符号的接口。 提供比更广泛的搜索[isymunmanagedbinder:: Getreaderforfile](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)方法。|  
  
## <a name="requirements"></a>惠?  
 **标头：** CorSym.idl、 CorSym.h  
  
## <a name="see-also"></a>请参阅  
 [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [ISymUnmanagedBinder 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 [ISymUnmanagedBinder3 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
