---
title: ISymUnmanagedBinder3 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3 Interface
helpviewer_keywords:
- ISymUnmanagedBinder3 interface [.NET Framework debugging]
ms.assetid: 37527a84-4b03-4f08-8135-94d898599089
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a6f514cc070a0a38eb09a5387efc8611100765b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944096"
---
# <a name="isymunmanagedbinder3-interface"></a>ISymUnmanagedBinder3 接口
扩展符号联编程序接口。 通过对`QueryInterface` `ISymUnmanagedBinder`实现接口的对象调用来获取此接口。  
  
> [!IMPORTANT]
> 打开不受信任的源中的程序数据库 (PDB) 文件会带来安全风险。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetReaderFromCallback 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-getreaderfromcallback-method.md)|允许用户通过回调`IID_IDiaReadExeAtRVACallback` `IID_IDiaReadExeAtOffsetCallback`来实现或提供, 以从内存中获取调试目录信息|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym, CorSym  
  
## <a name="see-also"></a>请参阅

- [诊断符号存储区接口](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [ISymUnmanagedBinder 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
- [ISymUnmanagedBinder2 接口](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
