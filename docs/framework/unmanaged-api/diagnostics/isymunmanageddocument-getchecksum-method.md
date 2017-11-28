---
title: "ISymUnmanagedDocument::GetCheckSum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b0b2ce6facf99b44f54e8880d4436ab7fe96e50a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="bb2c6-102">ISymUnmanagedDocument::GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="bb2c6-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="bb2c6-103">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="bb2c6-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb2c6-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb2c6-105">参数</span><span class="sxs-lookup"><span data-stu-id="bb2c6-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="bb2c6-106">[in]提供的缓冲区的长度`data`参数</span><span class="sxs-lookup"><span data-stu-id="bb2c6-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="bb2c6-107">[out]大小和校验和，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="bb2c6-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="bb2c6-108">[out]接收校验和的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="bb2c6-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb2c6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bb2c6-109">Return Value</span></span>  
 <span data-ttu-id="bb2c6-110">如果该方法成功; 则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="bb2c6-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2c6-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb2c6-111">See Also</span></span>  
 [<span data-ttu-id="bb2c6-112">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="bb2c6-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
