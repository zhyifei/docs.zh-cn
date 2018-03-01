---
title: "GetWin32ResBlob 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5f09bfd3ccfd3ac37854d70c226f40b17f86ccf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="1f35c-102">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="1f35c-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="1f35c-103">检索 Win32 资源 blob。</span><span class="sxs-lookup"><span data-stu-id="1f35c-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="1f35c-104">设置程序集选项后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="1f35c-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f35c-105">语法</span><span class="sxs-lookup"><span data-stu-id="1f35c-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1f35c-106">参数</span><span class="sxs-lookup"><span data-stu-id="1f35c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="1f35c-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="1f35c-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="1f35c-108">用于检索文件名构造 Win32 版本资源时要使用的文件标记</span><span class="sxs-lookup"><span data-stu-id="1f35c-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="1f35c-109">如果文件是 DLL，则返回 false 的 EXE，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="1f35c-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="1f35c-110">要插入到资源 blob 的可选图标。</span><span class="sxs-lookup"><span data-stu-id="1f35c-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="1f35c-111">接收资源 blob。</span><span class="sxs-lookup"><span data-stu-id="1f35c-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="1f35c-112">接收的 blob 的大小。</span><span class="sxs-lookup"><span data-stu-id="1f35c-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f35c-113">返回值</span><span class="sxs-lookup"><span data-stu-id="1f35c-113">Return Value</span></span>  
 <span data-ttu-id="1f35c-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="1f35c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f35c-115">惠?</span><span class="sxs-lookup"><span data-stu-id="1f35c-115">Requirements</span></span>  
 <span data-ttu-id="1f35c-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="1f35c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f35c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f35c-117">See Also</span></span>  
 [<span data-ttu-id="1f35c-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="1f35c-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="1f35c-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="1f35c-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="1f35c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="1f35c-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
