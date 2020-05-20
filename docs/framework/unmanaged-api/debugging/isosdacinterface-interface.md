---
title: ISOSDacInterface 接口
ms.date: 02/01/2019
api.name:
- ISOSDacInterface Interface
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface Interface
helpviewer.keywords:
- ISOSDacInterface Interface [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c9b4e6e5b36fe38b6c0ea78f6d1848d155008bcc
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420963"
---
# <a name="isosdacinterface-interface"></a><span data-ttu-id="46d74-102">ISOSDacInterface 接口</span><span class="sxs-lookup"><span data-stu-id="46d74-102">ISOSDacInterface Interface</span></span>

<span data-ttu-id="46d74-103">提供用于访问中的数据的帮助器方法 `SOS` 。</span><span class="sxs-lookup"><span data-stu-id="46d74-103">Provides helper methods to access data from `SOS`.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="methods"></a><span data-ttu-id="46d74-104">方法</span><span class="sxs-lookup"><span data-stu-id="46d74-104">Methods</span></span>

| <span data-ttu-id="46d74-105">方法</span><span class="sxs-lookup"><span data-stu-id="46d74-105">Method</span></span>                                                                                                               | <span data-ttu-id="46d74-106">说明</span><span class="sxs-lookup"><span data-stu-id="46d74-106">Description</span></span>                                                                                                                   |
| -------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| [<span data-ttu-id="46d74-107">GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="46d74-107">GetMethodDescData</span></span>](isosdacinterface-getmethoddescdata-method.md) | <span data-ttu-id="46d74-108">获取给定 MethodDesc 指针的数据。</span><span class="sxs-lookup"><span data-stu-id="46d74-108">Gets the data for the given MethodDesc pointer.</span></span> |
| [<span data-ttu-id="46d74-109">GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="46d74-109">GetMethodDescPtrFromIP</span></span>](isosdacinterface-getmethoddescptrfromip-method.md) | <span data-ttu-id="46d74-110">检索与包含给定本机指令地址的方法相对应的 MethodDesc 的指针。</span><span class="sxs-lookup"><span data-stu-id="46d74-110">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span> |
| [<span data-ttu-id="46d74-111">GetModuleData</span><span class="sxs-lookup"><span data-stu-id="46d74-111">GetModuleData</span></span>](isosdacinterface-getmoduledata-method.md)| <span data-ttu-id="46d74-112">提取与在给定地址加载的模块对应的数据。</span><span class="sxs-lookup"><span data-stu-id="46d74-112">Fetches the data corresponding to the module loaded at a given address.</span></span> |

## <a name="remarks"></a><span data-ttu-id="46d74-113">备注</span><span class="sxs-lookup"><span data-stu-id="46d74-113">Remarks</span></span>

<span data-ttu-id="46d74-114">此接口在运行时中存在，不会通过任何标头或库文件公开。</span><span class="sxs-lookup"><span data-stu-id="46d74-114">This interface lives inside the runtime and is not exposed through any headers or library files.</span></span> <span data-ttu-id="46d74-115">但是，它是从使用 GUID 派生的 COM 接口， `IUnknown` `436f00f2-b42a-4b9f-870c-e73db66ae930` 该接口可通过常用的 COM 机制获得。</span><span class="sxs-lookup"><span data-stu-id="46d74-115">However, it's a COM interface that derives from `IUnknown` with GUID `436f00f2-b42a-4b9f-870c-e73db66ae930` that can be obtained through the usual COM mechanisms.</span></span>

## <a name="requirements"></a><span data-ttu-id="46d74-116">要求</span><span class="sxs-lookup"><span data-stu-id="46d74-116">Requirements</span></span>

<span data-ttu-id="46d74-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="46d74-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="46d74-118">**标头：** 内容</span><span class="sxs-lookup"><span data-stu-id="46d74-118">**Header:** None</span></span>  
<span data-ttu-id="46d74-119">**库：** 内容</span><span class="sxs-lookup"><span data-stu-id="46d74-119">**Library:** None</span></span>  
<span data-ttu-id="46d74-120">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="46d74-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="46d74-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46d74-121">See also</span></span>

- [<span data-ttu-id="46d74-122">调试</span><span class="sxs-lookup"><span data-stu-id="46d74-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="46d74-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="46d74-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
