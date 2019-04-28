---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 191aa16c285b3a28beed65004d65525c9214ec93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650734"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="bf0d7-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="bf0d7-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="bf0d7-103">功能一样[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)只不过用终止的 null 字符，以使的固定的大小的字符串数据后面的零填充的路径字符串`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="bf0d7-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="bf0d7-104">填充仅有自身的路径字符串长度是否小于`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="bf0d7-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="bf0d7-105">这使得更轻松地编写该差异 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="bf0d7-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0d7-106">语法</span><span class="sxs-lookup"><span data-stu-id="bf0d7-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf0d7-107">参数</span><span class="sxs-lookup"><span data-stu-id="bf0d7-107">Parameters</span></span>  
  
|<span data-ttu-id="bf0d7-108">参数</span><span class="sxs-lookup"><span data-stu-id="bf0d7-108">Parameter</span></span>|<span data-ttu-id="bf0d7-109">描述</span><span class="sxs-lookup"><span data-stu-id="bf0d7-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="bf0d7-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bf0d7-110">Return Value</span></span>  
 <span data-ttu-id="bf0d7-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="bf0d7-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf0d7-112">要求</span><span class="sxs-lookup"><span data-stu-id="bf0d7-112">Requirements</span></span>  
 <span data-ttu-id="bf0d7-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bf0d7-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0d7-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf0d7-114">See also</span></span>

- [<span data-ttu-id="bf0d7-115">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="bf0d7-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
