---
title: ISymUnmanagedReader::GetSymbolStoreFileName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 147b33a3f49f9163daea776779ca26f62561a84e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170373"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="5559b-102">ISymUnmanagedReader::GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="5559b-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="5559b-103">提供在符号存储区的磁盘上的文件名称。</span><span class="sxs-lookup"><span data-stu-id="5559b-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5559b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5559b-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5559b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5559b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5559b-106">[in]大小`szName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5559b-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5559b-107">[out]指向接收长度中返回的名称的变量的指针`szName`，包括 null 终止。</span><span class="sxs-lookup"><span data-stu-id="5559b-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5559b-108">[out]指向接收符号存储区的文件名称的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="5559b-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5559b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5559b-109">Return Value</span></span>  
 <span data-ttu-id="5559b-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="5559b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5559b-111">要求</span><span class="sxs-lookup"><span data-stu-id="5559b-111">Requirements</span></span>  
 <span data-ttu-id="5559b-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5559b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5559b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5559b-113">See also</span></span>

- [<span data-ttu-id="5559b-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="5559b-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
