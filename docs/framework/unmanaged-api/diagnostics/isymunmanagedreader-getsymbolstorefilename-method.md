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
ms.openlocfilehash: b3674c4058dba2f6185418b55b35eefb14c312f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431238"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="97112-102">ISymUnmanagedReader::GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="97112-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="97112-103">提供符号存储区的磁盘上的文件名。</span><span class="sxs-lookup"><span data-stu-id="97112-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97112-104">语法</span><span class="sxs-lookup"><span data-stu-id="97112-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97112-105">参数</span><span class="sxs-lookup"><span data-stu-id="97112-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="97112-106">中`szName` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="97112-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="97112-107">弄指向变量的指针，该变量接收 `szName`中返回的名称的长度（包括 null 终止）。</span><span class="sxs-lookup"><span data-stu-id="97112-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="97112-108">弄指向接收符号存储区文件名的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="97112-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97112-109">返回值</span><span class="sxs-lookup"><span data-stu-id="97112-109">Return Value</span></span>  
 <span data-ttu-id="97112-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="97112-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97112-111">要求</span><span class="sxs-lookup"><span data-stu-id="97112-111">Requirements</span></span>  
 <span data-ttu-id="97112-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="97112-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97112-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97112-113">See also</span></span>

- [<span data-ttu-id="97112-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="97112-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
