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
ms.openlocfilehash: ff3103a46390c880a56ff443bfe20744f2ba0bfd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430690"
---
# <a name="getwin32resblob-method"></a><span data-ttu-id="7a611-102">GetWin32ResBlob 方法</span><span class="sxs-lookup"><span data-stu-id="7a611-102">GetWin32ResBlob Method</span></span>
<span data-ttu-id="7a611-103">检索 Win32 资源 blob。</span><span class="sxs-lookup"><span data-stu-id="7a611-103">Retrieves Win32 resource blob.</span></span> <span data-ttu-id="7a611-104">在设置程序集选项后调用此方法。</span><span class="sxs-lookup"><span data-stu-id="7a611-104">Call this method after setting assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a611-105">语法</span><span class="sxs-lookup"><span data-stu-id="7a611-105">Syntax</span></span>  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a611-106">参数</span><span class="sxs-lookup"><span data-stu-id="7a611-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7a611-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="7a611-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7a611-108">用于检索构造 Win32 版本资源时要使用的文件名的文件标记</span><span class="sxs-lookup"><span data-stu-id="7a611-108">File token used to retrieve the filename to be used when constructing the Win32 Version resource</span></span>  
  
 `fDll`  
 <span data-ttu-id="7a611-109">如果文件是 DLL，则为 TRUE; 对于 EXE，则为 false。</span><span class="sxs-lookup"><span data-stu-id="7a611-109">TRUE if file is a DLL, false for an EXE.</span></span>  
  
 `pszIconFile`  
 <span data-ttu-id="7a611-110">要插入资源 blob 的可选图标。</span><span class="sxs-lookup"><span data-stu-id="7a611-110">Optional icon to insert into the resource blob.</span></span>  
  
 `ppResBlob`  
 <span data-ttu-id="7a611-111">接收资源 blob。</span><span class="sxs-lookup"><span data-stu-id="7a611-111">Receives the resource blob.</span></span>  
  
 `pcbResBlob`  
 <span data-ttu-id="7a611-112">接收 blob 的大小。</span><span class="sxs-lookup"><span data-stu-id="7a611-112">Receives the size of the blob.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a611-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7a611-113">Return Value</span></span>  
 <span data-ttu-id="7a611-114">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7a611-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a611-115">要求</span><span class="sxs-lookup"><span data-stu-id="7a611-115">Requirements</span></span>  
 <span data-ttu-id="7a611-116">需要 alink</span><span class="sxs-lookup"><span data-stu-id="7a611-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a611-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a611-117">See also</span></span>

- [<span data-ttu-id="7a611-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="7a611-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7a611-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="7a611-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7a611-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="7a611-120">ALink API</span></span>](index.md)
