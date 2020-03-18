---
ms.openlocfilehash: cbd599f7467c3b360bbe1c76a65abfdb840a1530
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803266"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a>WPF 生成可冻结鼠标的 wisptis.exe 进程

|   |   |
|---|---|
|详细信息|4\.5.2 中引入了一个问题，导致生成可冻结鼠标输入的 <code>wisptis.exe</code>。|
|建议|.NET Framework 4.5.2 的服务版本（修补程序汇总 3026376）中提供了此问题的修补程序，也可通过升级到 .NET Framework 4.6 解决此问题|
|范围|主要|
|Version|4.5.2|
|类型|运行时|
