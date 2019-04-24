---
ms.openlocfilehash: ad624a665dbe8e989ea05acc20213809e515e6ac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803351"
---
### <a name="incorrect-code-generation-when-passing-and-comparing-uint16-values"></a>传递和比较 UInt16 值时，代码生成不正确

|   |   |
|---|---|
|详细信息|由于 .NET Framework 4.7 中引入了更改，在某些情况下，.NET Framework 4.7 上运行的应用程序中由 JIT 编译器生成的代码错误地比较了两个 <code>T:System.UInt16</code> 值。 有关详细信息，请参阅 GitHub.com 上的[问题 #11508：传递和比较 ushort 参数时不提示错误 codegen](https://github.com/dotnet/coreclr/issues/11508)。|
|建议|如果在 .NET Framework 4.7 中比较 16 位无符号值时遇到问题，请升级到 .NET Framework 4.7.1。|
|范围|边缘|
|Version|4.7|
|类型|运行时|
