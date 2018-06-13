---
title: GetWin32ResBlob 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f40b99c0a81bf0f2b622c7d23157dbb5736df1ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403287"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="c3752-102">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="c3752-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="c3752-103">检索 Win32 资源 blob。</span><span class="sxs-lookup"><span data-stu-id="c3752-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="c3752-104">设置程序集选项后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="c3752-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3752-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3752-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="c3752-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3752-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c3752-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="c3752-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c3752-108">用于检索文件名构造 Win32 版本资源时要使用的文件标记</span><span class="sxs-lookup"><span data-stu-id="c3752-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="c3752-109">如果文件是 DLL，则返回 false 的 EXE，则为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c3752-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="c3752-110">要插入到资源 blob 的可选图标。</span><span class="sxs-lookup"><span data-stu-id="c3752-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="c3752-111">接收资源 blob。</span><span class="sxs-lookup"><span data-stu-id="c3752-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="c3752-112">接收的 blob 的大小。</span><span class="sxs-lookup"><span data-stu-id="c3752-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3752-113">返回值</span><span class="sxs-lookup"><span data-stu-id="c3752-113">Return Value</span></span>  
 <span data-ttu-id="c3752-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="c3752-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3752-115">要求</span><span class="sxs-lookup"><span data-stu-id="c3752-115">Requirements</span></span>  
 <span data-ttu-id="c3752-116">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="c3752-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3752-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3752-117">See Also</span></span>  
 [<span data-ttu-id="c3752-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="c3752-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="c3752-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="c3752-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="c3752-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="c3752-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
