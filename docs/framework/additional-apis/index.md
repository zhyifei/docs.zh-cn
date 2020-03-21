---
title: 其他类库和 API
ms.date: 11/19/2019
helpviewer_keywords:
- Additional class libraries
- Additional managed libraries
- .NET Framework out-of-band releases
- out-of-band releases
ms.assetid: cf2d9006-b631-4e5d-81cd-20aab78c60f1
ms.topic: conceptual
ms.openlocfilehash: abf7fd20988ebaaaf1a40ccc168c636fd0dacc1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155903"
---
# <a name="additional-class-libraries-and-apis"></a>其他类库和 API

.NET 框架在不断发展。 为了改进跨平台开发并尽早引入新功能，新功能将发布在频段 （OOB） 外。 本主题列出了我们提供了有关文档的 OOB 项目。  
  
此外，一些库面向 .NET Framework 的特定平台或实现。 例如，<xref:System.Text.CodePagesEncodingProvider>类使代码页编码可用于使用 .NET 框架开发的 UWP 应用。 本主题还列出了以下库。  
  
## <a name="oob-projects"></a>OOB 项目
  
| Project | 说明 |  
| ------- | ----------- |  
| <xref:System.Collections.Immutable> | 提供的集合数是线程安全的，并且保证决不会更改该集合的内容。 |
| <xref:System.Net.Http.WinHttpHandler> | 基于 Windows 的 WinHTTP 接口为 <xref:System.Net.Http.HttpClient> 提供消息处理程序。 |
| <xref:System.Numerics> | 提供可利用基于 SIMD 硬件的加速的向量类型库。|
| <xref:System.Threading.Tasks.Dataflow> | TPL 数据流库提供数据流组件以帮助提高启用并发的应用程序的稳健性。 |  

## <a name="platform-specific-libraries"></a>特定于平台的库
  
| Project | 说明 |  
| ------- | ----------- |  
| <xref:System.Text.CodePagesEncodingProvider> | 扩展类<xref:System.Text.EncodingProvider>，使代码页编码可用于面向通用 Windows 平台的应用。 |  
  
## <a name="private-apis"></a>私有 API  

这些 API 支持产品基础结构，不应/不支持在代码中直接使用。  
  
* [微软.SqlServer.Server.Smiorder属性.项目属性](microsoft.sqlserver.server.smiorderproperty.item.md)
* [系统.例外.准备重新移动方法](system.exception.prepforremoting.md)
* [系统.数据.SqlTypes.SqlChars.流属性](system.data.sqltypes.sqlchars.stream.md)
* [系统.数据.SqlTypes.SqlStreamChars构造函数](system.data.sqltypes.sqlstreamchars.-ctor.md)
* [系统.数据.SqlTypes.SqlStreamChars.CanSeek 属性](system.data.sqltypes.sqlstreamchars.canseek.md)
* [系统.数据.SqlTypes.SqlStreamChars.IsNull 属性](system.data.sqltypes.sqlstreamchars.isnull.md)
* [系统.数据.SqlTypes.SqlStreamChars.长度属性](system.data.sqltypes.sqlstreamchars.length.md)
* [系统.数据.SqlTypes.SqlStreamChars.关闭方法](system.data.sqltypes.sqlstreamchars.close.md)
* [系统.数据.SqlTypes.SqlStreamChars.Dispose 方法](system.data.sqltypes.sqlstreamchars.dispose.md)
* [系统.数据.SqlTypes.SqlStreamChars.Flush 方法](system.data.sqltypes.sqlstreamchars.flush.md)
* [系统.数据.SqlTypes.SqlStreamChars.读取方法](system.data.sqltypes.sqlstreamchars.read.md)
* [系统.数据.SqlTypes.SqlStreamChars.查找方法](system.data.sqltypes.sqlstreamchars.seek.md)
* [系统.数据.SqlTypes.SqlStreamChars.set 长度方法](system.data.sqltypes.sqlstreamchars.setlength.md)
* [系统.数据.SqlTypes.SqlStreamChars.写入方法](system.data.sqltypes.sqlstreamchars.write.md)
* [系统.IO.内存流.内部获取源和长度方法](system.io.memorystream.internalgetoriginandlength.md)
* [系统.Net.连接类](connection.md)
* [系统.Net.连接.m\_写入列表字段](m_writelist.md)
* [系统.Net.连接组类](connectiongroup.md)
* [系统.Net.连接组.m\_连接列表字段](m_connectionlist.md)
* [系统.Net.连接流.连接属性](system.net.connectstream.connection.md)
* [系统.Net.核心响应数据类](coreresponsedata.md)
* [系统.Net.核心响应数据.m\_响应标题字段](coreresponsedata_m_responseheaders.md)
* [系统.Net.核心响应数据.m\_状态代码字段](coreresponsedata_m_statuscode.md)
* [系统.Net.HttpWeb请求。\_自动重定向字段](_autoredirects.md)
* [系统.Net.HttpWeb请求。\_核心响应字段](httpwebrequest__coreresponse.md)
* [系统.Net.HttpWeb请求。\_Http 响应字段](_httpresponse.md)
* [系统.Net.池流.网络流属性](system.net.pooledstream.networkstream.md)
* [系统.Net.RtcState 类](system.net.rtcstate.md)
* [系统.Net.服务点.m\_连接组列表字段](m_connectiongrouplist.md)
* [系统.Net.服务点管理器.的服务\_点表字段](s_servicepointtable.md)
* [系统.Net.TlsStream.m_Worker字段](system.net.tlsstream.m_worker.md)
* [系统.Net.Security.SslState.Ssl协议属性](system.net.security.sslstate.sslprotocol.md)
* [系统.服务模式.通道.消息.正文string方法](system.servicemodel.channels.message.bodytostring.md)
* [系统.服务模式.通道.消息.编写开始标题方法](system.servicemodel.channels.message.writestartheaders.md)
* [系统.Windows.诊断.视觉诊断是\_调试器检查禁用的"测试目的"字段](s-isdebuggercheckdisabledfortestpurposes-field.md)
* [系统.Windows.窗体.设计.数据成员字段编辑器类](datamemberfieldeditor-class.md)
* [系统.Windows.窗体.设计.数据成员列表编辑器类](datamemberlisteditor-class.md)
* [系统.Xml.XmlReader.createSqlReader方法](system.xml.xmlreader.createsqlreader.md)
* [阿多德布连接接口](adodb.connection.md)
* [阿多德布事件原因枚举](adodb.eventreasonenum.md)
* [阿多德布事件状态枚举](adodb.eventstatusenum.md)
* [stdole。DISPPARAMS 结构](stdole.dispparams.md)
* [stdole。EXCEPINFO 结构](stdole.excepinfo.md)
* [stdole。IFont.Name酒店](stdole.ifont.name.md)
* [stdole。IFontDisp 接口](stdole.ifontdisp.md)
* [stdole。IPicture.Handle 属性](stdole.ipicture.handle.md)
* [stdole。IPictureDisp.Handle 属性](stdole.ipicturedisp.handle.md)
* [stdole。斯特芬接口](stdole.stdfont.md)
* [stdole。StdPicture 界面](stdole.stdpicture.md)
  
## <a name="see-also"></a>另请参阅

* [.NET Framework 和带外版本](../get-started/the-net-framework-and-out-of-band-releases.md)
