---
title: "如何：使用 FTP 列出目录内容"
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
ms.assetid: 130c64c9-7b7f-4672-9b3b-d946bd2616c5
caps.latest.revision: 5
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 08edb5be23d55a9a825ca80a8e575cb02b5f07a8
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-list-directory-contents-with-ftp"></a><span data-ttu-id="a3818-102">如何：使用 FTP 列出目录内容</span><span class="sxs-lookup"><span data-stu-id="a3818-102">How to: List Directory Contents with FTP</span></span>
<span data-ttu-id="a3818-103">此示例演示如何列出 FTP 服务器的目录内容。</span><span class="sxs-lookup"><span data-stu-id="a3818-103">This sample shows how to list the directory contents of an FTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3818-104">示例</span><span class="sxs-lookup"><span data-stu-id="a3818-104">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main ()  
        {  
            // Get the object used to communicate with the server.  
            FtpWebRequest request = (FtpWebRequest)WebRequest.Create("ftp://www.contoso.com/");  
            request.Method = WebRequestMethods.Ftp.ListDirectoryDetails;  
  
            // This example assumes the FTP site uses anonymous logon.  
            request.Credentials = new NetworkCredential ("anonymous","janeDoe@contoso.com");  
  
            FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
  
            Stream responseStream = response.GetResponseStream();  
            StreamReader reader = new StreamReader(responseStream);  
            Console.WriteLine(reader.ReadToEnd());  
  
            Console.WriteLine("Directory List Complete, status {0}", response.StatusDescription);  
  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a3818-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="a3818-105">Compiling the Code</span></span>  
 <span data-ttu-id="a3818-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="a3818-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a3818-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="a3818-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a3818-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="a3818-108">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a3818-109">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="a3818-109">.NET Framework Security</span></span>

