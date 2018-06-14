---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 2030ad0ac00419280b45555ff11495c74e4274e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547780"
---
# <a name="ienumrawinputdevice"></a>IEnumRAWINPUTDEVICE
此接口枚举原始输入设备，并仅供 PresentationHost.exe 使用。  
  
> [!NOTE]
>  此 API 预期仅支持在本地客户端计算机上使用  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)|在枚举器列表中枚举下一个 `celt` 元素（即 RAWINPUTDEVICE 结构），将它们和 `rgelt` 中枚举元素的实际数量返回至 `pceltFetched`。|  
|[IEnumRAWINPUTDEVIC:Skip](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-skip.md)|指示枚举数跳过下一步`celt`枚举中的元素，以便下一次调用到[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)不会返回这些元素。|  
|[IEnumRAWINPUTDEVIC:Reset](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-reset.md)|将枚举序列重置到开头。|  
|[IEnumRAWINPUTDEVIC:Clone](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-clone.md)|创建一个与当权枚举器相同状态的原始输入设备枚举器，以循环访问相同的列表。|  
  
## <a name="see-also"></a>请参阅  
 [有关原始输入](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/aboutrawinput.asp)
