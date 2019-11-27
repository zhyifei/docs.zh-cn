---
title: 其他类库和 API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
author: mairaw
ms.author: mairaw
ms.topic: conceptual
ms.openlocfilehash: e1e2af584c73b1c0b2548cdd3fcbd8517dfa330d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429337"
---
# <a name="additional-class-libraries-and-apis"></a>其他类库和 API

.NET Framework 不断发展。 若要改善跨平台开发并及早引入新功能，可通过带外（OOB）发布新功能。 本主题列出了我们提供了有关文档的 OOB 项目。  
  
此外，一些库面向 .NET Framework 的特定平台或实现。 例如，<xref:System.Text.CodePagesEncodingProvider> 类使代码页编码可用于使用 .NET Framework 开发的 UWP 应用。 本主题还列出了以下库。  
  
## <a name="oob-projects"></a>OOB 项目
  
| 项目 | 说明 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 提供的集合数是线程安全的，并且保证决不会更改该集合的内容。 |
| <xref:System.Net.Http.WinHttpHandler> | 基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。 |
| <xref:System.Numerics> | 提供可利用基于 SIMD 硬件的加速的向量类型库。| 
| <xref:System.Threading.Tasks.Dataflow> | TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。 |  

## <a name="platform-specific-libraries"></a>特定于平台的库
  
| 项目 | 说明 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | 扩展 <xref:System.Text.EncodingProvider> 类，使代码页编码可用于面向通用 Windows 平台的应用程序。 |  
  
## <a name="private-apis"></a>私有 API  

这些 API 支持产品基础结构，不应/不支持在代码中直接使用。  
  
* [SmiOrderProperty 属性（& e）](microsoft.sqlserver.server.smiorderproperty.item.md)
* [PrepForRemoting 方法](system.exception.prepforremoting.md)
* [SqlTypes. SqlChars 属性](system.data.sqltypes.sqlchars.stream.md)
* [SqlTypes. SqlStreamChars 构造函数](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [SqlTypes. SqlStreamChars. CanSeek 属性](system.data.sqltypes.sqlstreamchars.canseek.md)
* [SqlTypes. SqlStreamChars 属性](system.data.sqltypes.sqlstreamchars.isnull.md)
* [SqlTypes. SqlStreamChars 属性](system.data.sqltypes.sqlstreamchars.length.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.close.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.dispose.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.flush.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.read.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.seek.md)
* [SqlTypes. SqlStreamChars. SetLength 方法](system.data.sqltypes.sqlstreamchars.setlength.md)
* [SqlTypes. SqlStreamChars 方法](system.data.sqltypes.sqlstreamchars.write.md)
* [MemoryStream. InternalGetOriginAndLength 方法](system.io.memorystream.internalgetoriginandlength.md)
* [系统 .Net. 连接类](connection.md)
* [系统\_WriteList 字段](m_writelist.md)
* [ConnectionGroup 类](connectiongroup.md)
* [ConnectionGroup\_ConnectionList 字段](m_connectionlist.md)
* [系统 ConnectStream 属性](system.net.connectstream.connection.md)
* [CoreResponseData 类](coreresponsedata.md)
* [CoreResponseData\_ResponseHeaders 字段](coreresponsedata_m_responseheaders.md)
* [系统 CoreResponseData\_StatusCode 字段](coreresponsedata_m_statuscode.md)
* [HttpWebRequest.\_AutoRedirects 字段](_autoredirects.md)
* [HttpWebRequest.\_CoreResponse 字段](httpwebrequest__coreresponse.md)
* [HttpWebRequest.\_Httpresponse.cache 字段](_httpresponse.md)
* [PooledStream. NetworkStream 属性](system.net.pooledstream.networkstream.md)
* [RtcState 类](system.net.rtcstate.md)
* [ServicePoint\_ConnectionGroupList 字段](m_connectiongrouplist.md)
* [ServicePointManager\_ServicePointTable 字段](s_servicepointtable.md)
* [系统 m_Worker 字段 TlsStream](system.net.tlsstream.m_worker.md)
* [SslState. SslProtocol 属性](system.net.security.sslstate.sslprotocol.md)
* [System.servicemodel. BodyToString 方法](system.servicemodel.channels.message.bodytostring.md)
* [System.servicemodel. WriteStartHeaders 方法](system.servicemodel.channels.message.writestartheaders.md)
* [VisualDiagnostics\_"isDebuggerCheckDisabledForTestPurposes" 字段](s-isdebuggercheckdisabledfortestpurposes-field.md)
* ["DataMemberFieldEditor" 类](datamemberfieldeditor-class.md)
* ["DataMemberListEditor" 类](datamemberlisteditor-class.md)
* [System.web. CreateSqlReader 方法](system.xml.xmlreader.createsqlreader.md)
* [adodb.recordset.连接接口](adodb.connection.md)
* [adodb.recordset.EventReason 枚举](adodb.eventreasonenum.md)
* [adodb.recordset.EventStatus 枚举](adodb.eventstatusenum.md)
* [stdole.DISPPARAMS 结构](stdole.dispparams.md)
* [stdole.EXCEPINFO 结构](stdole.excepinfo.md)
* [stdole.IFont.Name 属性](stdole.ifont.name.md)
* [stdole.IFontDisp 接口](stdole.ifontdisp.md)
* [stdole.IPicture 属性](stdole.ipicture.handle.md)
* [stdole.IPictureDisp 属性](stdole.ipicturedisp.handle.md)
* [stdole.StdFont 接口](stdole.stdfont.md)
* [stdole.StdPicture 接口](stdole.stdpicture.md)
  
## <a name="see-also"></a>另请参阅

* [.NET Framework 和带外版本](../get-started/the-net-framework-and-out-of-band-releases.md)
