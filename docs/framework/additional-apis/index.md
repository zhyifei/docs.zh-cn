---
title: 其他类库和 API
ms.date: 01/29/2018
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: 0aed6f32bbd3ffdc9446e9d17be2d90c62444ee1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053240"
---
# <a name="additional-class-libraries-and-apis"></a>其他类库和 API

.NET Framework 不断发展。 若要改善跨平台开发并及早引入新功能，可通过带外（OOB）发布新功能。 本主题列出了我们提供了有关文档的 OOB 项目。  
  
此外，一些库面向 .NET Framework 的特定平台或实现。 例如， <xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用 .NET Framework 开发的 UWP 应用。 本主题还列出了以下库。  
  
## <a name="oob-projects"></a>OOB 项目
  
| 项目 | 描述 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 提供的集合数是线程安全的，并且保证决不会更改该集合的内容。 |
| <xref:System.Net.Http.WinHttpHandler> | 基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。 |
| <xref:System.Numerics> | 提供可利用基于 SIMD 硬件的加速的向量类型库。| 
| <xref:System.Threading.Tasks.Dataflow> | TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。 |  

## <a name="platform-specific-libraries"></a>特定于平台的库
  
| 项目 | 描述 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | <xref:System.Text.EncodingProvider>扩展类，使代码页编码可用于面向通用 Windows 平台的应用程序。 |  
  
## <a name="private-apis"></a>私有 API  

这些 API 支持产品基础结构，不应/不支持在代码中直接使用。  
  
| API 名称 |
| -------- |
| [系统 .Net. 连接类](connection.md) |
| [\_系统 WriteList 字段](m_writelist.md) |
| [ConnectionGroup 类](connectiongroup.md) |
| [系统 ConnectionGroup\_ConnectionList 字段](m_connectionlist.md) |
| [CoreResponseData 类](coreresponsedata.md) |
| [系统 CoreResponseData\_ResponseHeaders 字段](coreresponsedata_m_responseheaders.md) |
| [系统 CoreResponseData\_StatusCode 字段](coreresponsedata_m_statuscode.md) |
| [系统 HttpWebRequest。\_AutoRedirects 字段](_autoredirects.md) |
| [系统 HttpWebRequest。\_CoreResponse 字段](httpwebrequest__coreresponse.md) |
| [系统 HttpWebRequest。\_Httpresponse.cache 字段](_httpresponse.md) |
| [系统 ServicePoint\_ConnectionGroupList 字段](m_connectiongrouplist.md) |
| [系统 ServicePointManager\_ServicePointTable 字段](s_servicepointtable.md) |
| [VisualDiagnostics. s\_isDebuggerCheckDisabledForTestPurposes 字段](s-isdebuggercheckdisabledfortestpurposes-field.md) |
| ["DataMemberFieldEditor" 类](datamemberfieldeditor-class.md) |
| ["DataMemberListEditor" 类](datamemberlisteditor-class.md) |
  
## <a name="see-also"></a>请参阅

- [.NET Framework 和带外版本](../get-started/the-net-framework-and-out-of-band-releases.md)
