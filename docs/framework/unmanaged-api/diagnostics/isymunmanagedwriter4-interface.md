---
title: ISymUnmanagedWriter4 接口
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5732cc08512df25a14cc8ea9dcaa03c56207dde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202028"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="27df1-102">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="27df1-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="27df1-103">ISymUnmanagedWriter4 接口。</span><span class="sxs-lookup"><span data-stu-id="27df1-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27df1-104">语法</span><span class="sxs-lookup"><span data-stu-id="27df1-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="27df1-105">方法</span><span class="sxs-lookup"><span data-stu-id="27df1-105">Methods</span></span>  
 <span data-ttu-id="27df1-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="27df1-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="27df1-107">方法</span><span class="sxs-lookup"><span data-stu-id="27df1-107">Method</span></span>|<span data-ttu-id="27df1-108">描述</span><span class="sxs-lookup"><span data-stu-id="27df1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27df1-109">GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="27df1-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="27df1-110">功能一样[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)只不过用终止的 null 字符，以使的固定的大小的字符串数据后面的零填充的路径字符串`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="27df1-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="27df1-111">填充仅有自身的路径字符串长度是否小于`MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="27df1-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="27df1-112">这使得更轻松地编写该差异 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="27df1-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27df1-113">要求</span><span class="sxs-lookup"><span data-stu-id="27df1-113">Requirements</span></span>  
 <span data-ttu-id="27df1-114">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="27df1-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27df1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="27df1-115">See also</span></span>

- [<span data-ttu-id="27df1-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="27df1-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="27df1-117">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="27df1-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
