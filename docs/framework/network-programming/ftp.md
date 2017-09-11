---
title: FTP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- FTP
ms.assetid: 9b43f8b4-89d7-46a7-89fc-71aca916dd32
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2274873140c415a970884389e71163be7f4cba6
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="ftp"></a><span data-ttu-id="a2f2e-102">FTP</span><span class="sxs-lookup"><span data-stu-id="a2f2e-102">FTP</span></span>
<span data-ttu-id="a2f2e-103">.NET Framework 通过 <xref:System.Net.FtpWebRequest> 和 <xref:System.Net.FtpWebResponse> 类为 FTP 协议提供全面支持。</span><span class="sxs-lookup"><span data-stu-id="a2f2e-103">The .NET Framework provides comprehensive support for the FTP protocol with the <xref:System.Net.FtpWebRequest> and <xref:System.Net.FtpWebResponse> classes.</span></span> <span data-ttu-id="a2f2e-104">这些类派生自 <xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse>。</span><span class="sxs-lookup"><span data-stu-id="a2f2e-104">These classes are derived from <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="a2f2e-105">大多数情况下，<xref:System.Net.WebRequest> 和 <xref:System.Net.WebResponse> 类提供发出请求所需的所有事项，但如果需要访问作为属性公开的 FTP 特定功能，可以将这两个类转换为 <xref:System.Net.FtpWebRequest> 或 <xref:System.Net.FtpWebResponse>。</span><span class="sxs-lookup"><span data-stu-id="a2f2e-105">In most cases, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes provide all that is necessary to make the request, but if you need access to the FTP-specific features exposed as properties, you can typecast these classes to <xref:System.Net.FtpWebRequest> or <xref:System.Net.FtpWebResponse>.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a2f2e-106">示例</span><span class="sxs-lookup"><span data-stu-id="a2f2e-106">Examples</span></span>  
 <span data-ttu-id="a2f2e-107">有关详细信息，请参阅以下主题：[如何使用 FTP 下载文件](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md)、[如何使用 FTP 上传文件](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md)和[如何使用 FTP 列出目录内容](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md)。</span><span class="sxs-lookup"><span data-stu-id="a2f2e-107">For more information, see the following topics: [How to: Download Files with FTP](../../../docs/framework/network-programming/how-to-download-files-with-ftp.md), [How to: Upload Files with FTP](../../../docs/framework/network-programming/how-to-upload-files-with-ftp.md), and [How to: List Directory Contents with FTP](../../../docs/framework/network-programming/how-to-list-directory-contents-with-ftp.md).</span></span>  
  
## <a name="ftp-and-proxies"></a><span data-ttu-id="a2f2e-108">FTP 和代理</span><span class="sxs-lookup"><span data-stu-id="a2f2e-108">FTP and proxies</span></span>  
 <span data-ttu-id="a2f2e-109">如果代理（由 <xref:System.Net.FtpWebRequest.Proxy%2A> 属性指定）为 HTTP 代理，则仅支持 <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>、<xref:System.Net.WebRequestMethods.Ftp.ListDirectory> 和 <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> 命令。</span><span class="sxs-lookup"><span data-stu-id="a2f2e-109">If a proxy (specified by the <xref:System.Net.FtpWebRequest.Proxy%2A> property) is an HTTP proxy, then only the <xref:System.Net.WebRequestMethods.Ftp.DownloadFile>, <xref:System.Net.WebRequestMethods.Ftp.ListDirectory>, and <xref:System.Net.WebRequestMethods.Ftp.ListDirectoryDetails> commands are supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2f2e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2f2e-110">See Also</span></span>  
 <span data-ttu-id="a2f2e-111">[通过代理访问 Internet](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md) </span><span class="sxs-lookup"><span data-stu-id="a2f2e-111">[Accessing the Internet Through a Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md) </span></span>  
 <span data-ttu-id="a2f2e-112">[网络编程示例](../../../docs/framework/network-programming/network-programming-samples.md) </span><span class="sxs-lookup"><span data-stu-id="a2f2e-112">[Network Programming Samples](../../../docs/framework/network-programming/network-programming-samples.md) </span></span>  
 <span data-ttu-id="a2f2e-113">[FTP 客户端技术示例](http://go.microsoft.com/fwlink/?LinkID=179557) </span><span class="sxs-lookup"><span data-stu-id="a2f2e-113">[FTP Client Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179557) </span></span>  
 <span data-ttu-id="a2f2e-114">[FTP 资源管理器技术示例](http://go.microsoft.com/fwlink/?LinkID=179569) </span><span class="sxs-lookup"><span data-stu-id="a2f2e-114">[FTP Explorer Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179569) </span></span>  
 [<span data-ttu-id="a2f2e-115">使用应用程序协议</span><span class="sxs-lookup"><span data-stu-id="a2f2e-115">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)

