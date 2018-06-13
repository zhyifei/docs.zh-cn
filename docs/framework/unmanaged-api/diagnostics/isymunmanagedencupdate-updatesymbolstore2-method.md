---
title: ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 02eaaa1c3336b6e99b8c8deabb944e292e35a2a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425166"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="fa6b8-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 方法</span><span class="sxs-lookup"><span data-stu-id="fa6b8-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="fa6b8-103">允许编译器忽略未修改的程序数据库 (PDB) 流中的函数，提供行信息满足的要求。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="fa6b8-104">可使用旧的 PDB 行信息以及该函数中的所有行的一个增量确定正确的行信息。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa6b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="fa6b8-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa6b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="fa6b8-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="fa6b8-107">[in]指向的指针[IStream](https://msdn.microsoft.com/library/aa380034.aspx)包含行信息。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-107">[in] A pointer to an [IStream](https://msdn.microsoft.com/library/aa380034.aspx) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="fa6b8-108">[in]指向的指针[SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md)结构，其中包含已更改的行。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="fa6b8-109">[in]A `ULONG` ，它表示已更改的行数。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa6b8-110">返回值</span><span class="sxs-lookup"><span data-stu-id="fa6b8-110">Return Value</span></span>  
 <span data-ttu-id="fa6b8-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fa6b8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa6b8-112">要求</span><span class="sxs-lookup"><span data-stu-id="fa6b8-112">Requirements</span></span>  
 <span data-ttu-id="fa6b8-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fa6b8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa6b8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa6b8-114">See Also</span></span>  
 [<span data-ttu-id="fa6b8-115">ISymUnmanagedENCUpdate 接口</span><span class="sxs-lookup"><span data-stu-id="fa6b8-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
