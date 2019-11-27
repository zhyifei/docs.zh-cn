---
title: CreateALink 函数
ms.date: 03/30/2017
api_name:
- CreateALink
api_location:
- alink.dll
api_type:
- DLLExport
f1_keywords:
- CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type:
- apiref
ms.openlocfilehash: 9165a4db7e65fb0f409a902b06d32e9c2988aa69
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446553"
---
# <a name="createalink-function"></a><span data-ttu-id="1e400-102">CreateALink 函数</span><span class="sxs-lookup"><span data-stu-id="1e400-102">CreateALink Function</span></span>
<span data-ttu-id="1e400-103">创建程序集链接器的实例，并设置指向指定接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1e400-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e400-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e400-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e400-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e400-105">Parameters</span></span>  
  
|<span data-ttu-id="1e400-106">参数</span><span class="sxs-lookup"><span data-stu-id="1e400-106">Parameter</span></span>|<span data-ttu-id="1e400-107">说明</span><span class="sxs-lookup"><span data-stu-id="1e400-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="1e400-108">某个程序集链接器接口的物理名称。</span><span class="sxs-lookup"><span data-stu-id="1e400-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="1e400-109">成功完成后的位置包含指向 `riid` 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="1e400-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1e400-110">要求</span><span class="sxs-lookup"><span data-stu-id="1e400-110">Requirements</span></span>  
 <span data-ttu-id="1e400-111">**库**： alink</span><span class="sxs-lookup"><span data-stu-id="1e400-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e400-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1e400-112">See also</span></span>

- [<span data-ttu-id="1e400-113">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="1e400-113">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
