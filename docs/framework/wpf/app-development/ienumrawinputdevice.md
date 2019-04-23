---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 04caca0c580d26fde7fc9a3e3a11b7a8fed26d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225516"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="9dafe-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="9dafe-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="9dafe-103">此接口枚举原始输入设备，并仅供 PresentationHost.exe 使用。</span><span class="sxs-lookup"><span data-stu-id="9dafe-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dafe-104">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="9dafe-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="9dafe-105">成员</span><span class="sxs-lookup"><span data-stu-id="9dafe-105">Members</span></span>  
  
|<span data-ttu-id="9dafe-106">成员</span><span class="sxs-lookup"><span data-stu-id="9dafe-106">Member</span></span>|<span data-ttu-id="9dafe-107">描述</span><span class="sxs-lookup"><span data-stu-id="9dafe-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9dafe-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="9dafe-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="9dafe-109">在枚举器列表中枚举下一个 `celt` 元素（即 RAWINPUTDEVICE 结构），将它们和 `rgelt` 中枚举元素的实际数量返回至 `pceltFetched`。</span><span class="sxs-lookup"><span data-stu-id="9dafe-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="9dafe-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="9dafe-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="9dafe-111">指示枚举器跳过下一步`celt`枚举中的元素，以便下次调用[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md)不会返回这些元素。</span><span class="sxs-lookup"><span data-stu-id="9dafe-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="9dafe-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="9dafe-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="9dafe-113">将枚举序列重置到开头。</span><span class="sxs-lookup"><span data-stu-id="9dafe-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="9dafe-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="9dafe-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="9dafe-115">创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。</span><span class="sxs-lookup"><span data-stu-id="9dafe-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9dafe-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9dafe-116">See also</span></span>

- [<span data-ttu-id="9dafe-117">关于原始输入</span><span class="sxs-lookup"><span data-stu-id="9dafe-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
