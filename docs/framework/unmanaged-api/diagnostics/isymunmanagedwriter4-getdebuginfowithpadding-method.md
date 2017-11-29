---
title: "ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9f2f0aad37fcd63e2345cd32a00b44412ed8c7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="f434f-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="f434f-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="f434f-103">函数与相同[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)只不过用终止的 null 字符，以使的固定的大小的字符串数据后面的零填充的路径字符串`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="f434f-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="f434f-104">填充仅有自身的路径字符串长度是否小于`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="f434f-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="f434f-105">这会使易于编写该差异 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="f434f-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f434f-106">语法</span><span class="sxs-lookup"><span data-stu-id="f434f-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f434f-107">参数</span><span class="sxs-lookup"><span data-stu-id="f434f-107">Parameters</span></span>  
  
|<span data-ttu-id="f434f-108">参数</span><span class="sxs-lookup"><span data-stu-id="f434f-108">Parameter</span></span>|<span data-ttu-id="f434f-109">描述</span><span class="sxs-lookup"><span data-stu-id="f434f-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="f434f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="f434f-110">Return Value</span></span>  
 <span data-ttu-id="f434f-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="f434f-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f434f-112">要求</span><span class="sxs-lookup"><span data-stu-id="f434f-112">Requirements</span></span>  
 <span data-ttu-id="f434f-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f434f-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f434f-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f434f-114">See Also</span></span>  
 [<span data-ttu-id="f434f-115">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="f434f-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
