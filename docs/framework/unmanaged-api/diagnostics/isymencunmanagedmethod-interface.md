---
title: ISymENCUnmanagedMethod 接口
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod
helpviewer_keywords:
- ISymENCUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: faebf594-67d5-4abf-b9c1-547fd3a1ff87
topic_type:
- apiref
ms.openlocfilehash: 54c8c7f5c3ba6b4afd4ff352a8afb947a92e2d61
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441872"
---
# <a name="isymencunmanagedmethod-interface"></a>ISymENCUnmanagedMethod 接口
提供 "编辑并继续" 功能的信息。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetDocumentsForMethod 方法](isymencunmanagedmethod-getdocumentsformethod-method.md)|获取此方法在中具有线条的文档。|  
|[GetDocumentsForMethodCount 方法](isymencunmanagedmethod-getdocumentsformethodcount-method.md)|获取此方法在中包含行的文档数。|  
|[GetFileNameFromOffset 方法](isymencunmanagedmethod-getfilenamefromoffset-method.md)|获取与偏移量关联的行的文件名。|  
|[GetLineFromOffset 方法](isymencunmanagedmethod-getlinefromoffset-method.md)|获取与偏移量关联的行信息。|  
|[GetSourceExtentInDocument 方法](isymencunmanagedmethod-getsourceextentindocument-method.md)|获取特定文档中该方法的最小起始行和最大结束行。|  
  
## <a name="requirements"></a>要求  
 **标头：** CorSym，CorSym  
  
## <a name="see-also"></a>另请参阅

- [诊断符号存储区接口](diagnostics-symbol-store-interfaces.md)
