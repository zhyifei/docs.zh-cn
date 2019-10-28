---
ms.openlocfilehash: 6bb8c87af66e744514fb43e628c6423487342ac2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "72887734"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a>在启用触摸的系统上调用 System.Windows.Input.PenContext.Disable 可能会引发 ArgumentException

|   |   |
|---|---|
|详细信息|在某些情况下，在启用触摸的系统上调用内部 **System.Windows.Intput.PenContext.Disable** 方法可能会因为重新进入而引发未处理的 <code>T:System.ArgumentException</code>。|
|建议|此问题已在 .NET Framework 4.7 中得到解决。 若要避免此异常，升级到 .NET Framework 4.7 及以上版本。|
|范围|边缘|
|版本|4.6.1|
|类型|重定目标|
