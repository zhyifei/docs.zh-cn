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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 11117db08d58684cc854400424d1836ec35b8c12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497999"
---
# <a name="createalink-function"></a><span data-ttu-id="8470d-102">CreateALink 函数</span><span class="sxs-lookup"><span data-stu-id="8470d-102">CreateALink Function</span></span>
<span data-ttu-id="8470d-103">创建程序集链接器的实例并设置为指定接口的指针。</span><span class="sxs-lookup"><span data-stu-id="8470d-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8470d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8470d-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8470d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8470d-105">Parameters</span></span>  
  
|<span data-ttu-id="8470d-106">参数</span><span class="sxs-lookup"><span data-stu-id="8470d-106">Parameter</span></span>|<span data-ttu-id="8470d-107">描述</span><span class="sxs-lookup"><span data-stu-id="8470d-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="8470d-108">一个程序集链接器接口的物理名称。</span><span class="sxs-lookup"><span data-stu-id="8470d-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="8470d-109">在成功完成，包含一个指向的位置`riid`接口。</span><span class="sxs-lookup"><span data-stu-id="8470d-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8470d-110">要求</span><span class="sxs-lookup"><span data-stu-id="8470d-110">Requirements</span></span>  
 <span data-ttu-id="8470d-111">**库**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="8470d-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8470d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="8470d-112">See also</span></span>
- [<span data-ttu-id="8470d-113">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="8470d-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
