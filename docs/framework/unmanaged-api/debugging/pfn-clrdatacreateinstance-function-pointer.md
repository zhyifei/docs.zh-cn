---
title: PFN_CLRDataCreateInstance 函数指针
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
ms.openlocfilehash: 34aae3cd913465bc3167d6c5eee9873d212fa4ac
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420679"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="1c7b9-102">PFN_CLRDataCreateInstance 函数指针</span><span class="sxs-lookup"><span data-stu-id="1c7b9-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="1c7b9-103">指向一个函数，该函数为指定的目标项创建接口对象。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c7b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c7b9-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c7b9-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c7b9-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="1c7b9-106">中要实例化的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="1c7b9-107">中一个指向用户实现的[ICLRDataTarget](iclrdatatarget-interface.md)对象的指针，该对象表示要为其创建 interface 对象的目标项。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="1c7b9-108">弄指向返回的接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c7b9-109">备注</span><span class="sxs-lookup"><span data-stu-id="1c7b9-109">Remarks</span></span>  
 <span data-ttu-id="1c7b9-110">`ICLRDataTarget`对象由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="1c7b9-111">实现取决于所表示的目标项的类型。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="1c7b9-112">目标项可以是进程、内存转储、远程计算机，等等。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c7b9-113">要求</span><span class="sxs-lookup"><span data-stu-id="1c7b9-113">Requirements</span></span>  
 <span data-ttu-id="1c7b9-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c7b9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c7b9-115">**标头：** ClrData .idl</span><span class="sxs-lookup"><span data-stu-id="1c7b9-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="1c7b9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c7b9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c7b9-117">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c7b9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7b9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c7b9-118">See also</span></span>

- [<span data-ttu-id="1c7b9-119">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="1c7b9-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
