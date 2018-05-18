---
title: FTP
ms.date: 03/30/2017
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e491754b1c6c96e6afa9b172200cfb564307a8a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ftp"></a>FTP
.NET Framework 通过 <xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 类为 FTP 协议提供全面支持。 这些类派生自 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>。 大多数情况下，<xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类提供发出请求所需的所有事项，但如果需要访问作为属性公开的 FTP 特定功能，可以将这两个类转换为 <xref:System.Net.FtpWebRequest> 或 <xref:System.Net.FtpWebResponse>。  
  
## <a name="examples"></a>示例  
 有关详细信息，请参阅以下主题：[如何使用 FTP 下载文件](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md)、[如何使用 FTP 上传文件](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md)和[如何使用 FTP 列出目录内容](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md)。  
  
## <a name="ftp-and-proxies"></a>FTP 和代理  
 如果代理（由 <xref:System.Net.FtpWebRequest.Proxy%2A> 属性指定）为 HTTP 代理，则仅支持 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>、<xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 和 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 命令。  
  
## <a name="see-also"></a>请参阅  
 [通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md)  
 [FTP 客户端技术示例](http://go.microsoft.com/fwlink/?LinkID=179557)  
 [FTP 资源管理器技术示例](http://go.microsoft.com/fwlink/?LinkID=179569)  
 [使用应用程序协议](../../../docs/framework/network-programming/using-application-protocols.md)
