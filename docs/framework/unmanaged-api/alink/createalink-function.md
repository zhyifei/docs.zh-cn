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
ms.openlocfilehash: b494b8b776f4cb0eb534233c5a03ab2d34a698ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115617"
---
# <a name="createalink-function"></a><span data-ttu-id="abb78-102">CreateALink 函数</span><span class="sxs-lookup"><span data-stu-id="abb78-102">CreateALink Function</span></span>
<span data-ttu-id="abb78-103">创建程序集链接器的实例并设置为指定接口的指针。</span><span class="sxs-lookup"><span data-stu-id="abb78-103">Creates an instance of the Assembly Linker and sets a pointer to the specified interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abb78-104">语法</span><span class="sxs-lookup"><span data-stu-id="abb78-104">Syntax</span></span>  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="abb78-105">参数</span><span class="sxs-lookup"><span data-stu-id="abb78-105">Parameters</span></span>  
  
|<span data-ttu-id="abb78-106">参数</span><span class="sxs-lookup"><span data-stu-id="abb78-106">Parameter</span></span>|<span data-ttu-id="abb78-107">描述</span><span class="sxs-lookup"><span data-stu-id="abb78-107">Description</span></span>|  
|---------------|-----------------|  
|`riid`|<span data-ttu-id="abb78-108">一个程序集链接器接口的物理名称。</span><span class="sxs-lookup"><span data-stu-id="abb78-108">The physical name of one of the Assembly Linker interfaces.</span></span>|  
|`ppInterface`|<span data-ttu-id="abb78-109">在成功完成，包含一个指向的位置`riid`接口。</span><span class="sxs-lookup"><span data-stu-id="abb78-109">The location that on successful completion contains a pointer to the `riid` interface.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abb78-110">要求</span><span class="sxs-lookup"><span data-stu-id="abb78-110">Requirements</span></span>  
 <span data-ttu-id="abb78-111">**库**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="abb78-111">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abb78-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="abb78-112">See also</span></span>

- [<span data-ttu-id="abb78-113">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="abb78-113">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
