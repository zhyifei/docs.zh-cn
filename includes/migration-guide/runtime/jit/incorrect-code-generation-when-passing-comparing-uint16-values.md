---
ms.openlocfilehash: b23909c53b451b4b18bf0ccdf59f51e7c8e3114f
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802470"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>传递和比较 UInt16 值时，代码生成不正确

|   |   |
|---|---|
|详细信息|由于 .NET Framework 4.7 中引入了更改，在某些情况下，.NET Framework 4.7 上运行的应用程序中由 JIT 编译器生成的代码错误地比较了两个 <code>T:System.UInt16</code> 值。 有关详细信息，请参阅 GitHub.com 上的[问题 #11508：传递和比较 ushort 参数时不提示错误 codegen](https://github.com/dotnet/coreclr/issues/11508)。|
|建议|如果在 .NET Framework 4.7 中比较 16 位无符号值时遇到问题，请升级到 .NET Framework 4.7.1。|
|范围|边缘|
|Version|4.7|
|类型|运行时|

