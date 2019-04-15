---
ms.openlocfilehash: 6309cead46dff44ff6360bac9b31666f875be210
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235078"
---
### <a name="marshalsizeof-and-marshalptrtostructure-overloads-break-dynamic-code"></a>Marshal.SizeOf 和 Marshal.PtrToStructure 重载中断动态代码

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5.1 开始，动态绑定到方法 <xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601>、<xref:System.Runtime.InteropServices.Marshal.SizeOf%60%601(%60%600)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Object)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure(System.IntPtr,System.Type)>、<xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr)> 或 <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%60%601(System.IntPtr,%60%600)>（例如通过 Windows PowerShell、IronPython 或 C# dynamic 关键字）将引发 <code>MethodInvocationExceptions</code>，因为这些方法的新重载已添加，使得对于脚本引擎而言可能不明确。|
|建议|更新脚本以清楚指示应使用哪个重载。 通常，这可通过将方法的类型参数显式转换为 <xref:System.Type> 来实现。 有关如何解决此问题的详细信息和示例，请参阅[此链接](https://support.microsoft.com/kb/2909958/)。|
|范围|次要|
|版本|4.5.1|
|类型|运行时|
