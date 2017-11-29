---
title: "ISymUnmanagedReader::GetSymbolStoreFileName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetSymbolStoreFileName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 951dfd45f6b313b6cde28f3f65f2799380a33a78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="b13b4-102">ISymUnmanagedReader::GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="b13b4-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="b13b4-103">提供符号存储区的磁盘上的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b13b4-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="b13b4-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b13b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="b13b4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b13b4-106">[in]大小`szName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b13b4-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b13b4-107">[out]指向接收中返回的名称的长度变量的指针`szName`，包括 null 终止。</span><span class="sxs-lookup"><span data-stu-id="b13b4-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="b13b4-108">[out]指向接收符号存储区的文件名称的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="b13b4-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b13b4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b13b4-109">Return Value</span></span>  
 <span data-ttu-id="b13b4-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b13b4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13b4-111">要求</span><span class="sxs-lookup"><span data-stu-id="b13b4-111">Requirements</span></span>  
 <span data-ttu-id="b13b4-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b13b4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13b4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b13b4-113">See Also</span></span>  
 [<span data-ttu-id="b13b4-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="b13b4-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
