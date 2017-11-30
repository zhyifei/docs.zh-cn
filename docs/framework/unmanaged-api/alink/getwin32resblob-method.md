---
title: "GetWin32ResBlob 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink.GetWin32ResBlob
api_location: alink.dll
api_type: COM
f1_keywords: GetWin32ResBlob
helpviewer_keywords: GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9c4456757c56440463010d4adc3d3eed90dbc07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="4c3b3-102">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="4c3b3-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="4c3b3-103">检索 Win32 资源 blob。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="4c3b3-104">设置程序集选项后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c3b3-105">语法</span><span class="sxs-lookup"><span data-stu-id="4c3b3-105">Syntax</span></span>  
  
```  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c3b3-106">参数</span><span class="sxs-lookup"><span data-stu-id="4c3b3-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="4c3b3-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4c3b3-108">用于检索文件名构造 Win32 版本资源时要使用的文件标记</span><span class="sxs-lookup"><span data-stu-id="4c3b3-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="4c3b3-109">如果文件是 DLL，则返回 false 的 EXE，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="4c3b3-110">要插入到资源 blob 的可选图标。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="4c3b3-111">接收资源 blob。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="4c3b3-112">接收的 blob 的大小。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c3b3-113">返回值</span><span class="sxs-lookup"><span data-stu-id="4c3b3-113">Return Value</span></span>  
 <span data-ttu-id="4c3b3-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="4c3b3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c3b3-115">要求</span><span class="sxs-lookup"><span data-stu-id="4c3b3-115">Requirements</span></span>  
 <span data-ttu-id="4c3b3-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="4c3b3-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c3b3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c3b3-117">See Also</span></span>  
 [<span data-ttu-id="4c3b3-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="4c3b3-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4c3b3-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="4c3b3-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4c3b3-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="4c3b3-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
