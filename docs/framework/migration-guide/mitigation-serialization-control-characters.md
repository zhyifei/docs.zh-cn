---
title: 使用 DataContractJsonSerializer 对控制字符进行序列化
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
ms.openlocfilehash: 209f7827e61ef72de1d64fad46dc9f241fa6edef
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346576"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>缓解：使用 DataContractJsonSerializer 对控制字符进行序列化

自 .NET Framework 4.7 起，使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 对控制字符进行序列化的方式已更改为与 ECMAScript V6 和 V8 兼容。 
 
## <a name="impact"></a>影响

在 .NET framework 4.6.2 及更低版本中，<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 未按与 ECMAScript V6 和 V8 标准兼容的方式对一些特殊控制字符（如 `\b`、`\f` 和 `\t`）进行序列化。

对于定位 .NET Framework 4.7 及更高版本的应用程序，这些控制字符的序列化与 ECMAScript V6 和 V8 兼容。 以下 API 受到影响：

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 

## <a name="mitigation"></a>缓解

对于定位 .NET Framework 4.7 及更高版本的应用程序，此行为默认启用。

如果不需要此行为，可以在 app.config 或 web.config 文件的 `<runtime>` 部分中添加下面的代码行，从而选择禁用此功能：

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>请参阅

- [应用程序兼容性](application-compatibility.md)
