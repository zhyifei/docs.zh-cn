---
title: 如何：使用 FTP 上载文件
ms.date: 03/30/2017
ms.assetid: e40f17c5-dd12-4c62-9dbf-00ab491382dc
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d032c171188f8a9536276c3cfe46392f90567bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393024"
---
# <a name="how-to-upload-files-with-ftp"></a><span data-ttu-id="35e69-102">如何：使用 FTP 上载文件</span><span class="sxs-lookup"><span data-stu-id="35e69-102">How to: Upload Files with FTP</span></span>
<span data-ttu-id="35e69-103">此示例演示如何上传文件到 FTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="35e69-103">This sample shows how to upload a file to an FTP server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35e69-104">示例</span><span class="sxs-lookup"><span data-stu-id="35e69-104">Example</span></span>  
  
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
            FtpWebRequest request = (FtpWebRequest)WebRequest.Create("ftp://www.contoso.com/test.htm");
            request.Method = WebRequestMethods.Ftp.UploadFile;

            // This example assumes the FTP site uses anonymous logon.  
            request.Credentials = new NetworkCredential("anonymous", "janeDoe@contoso.com");

            // Copy the contents of the file to the request stream.  
            byte[] fileContents;
            using (StreamReader sourceStream = new StreamReader("testfile.txt"))
            {
                fileContents = Encoding.UTF8.GetBytes(sourceStream.ReadToEnd());
            }
            
            request.ContentLength = fileContents.Length;

            using (Stream requestStream = request.GetRequestStream())
            {
                requestStream.Write(fileContents, 0, fileContents.Length);
            }

            using (FtpWebResponse response = (FtpWebResponse)request.GetResponse())
            {
                Console.WriteLine("Upload File Complete, status {0}", response.StatusDescription);
            }
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="35e69-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="35e69-105">Compiling the Code</span></span>  
 <span data-ttu-id="35e69-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="35e69-106">This example requires:</span></span>  
  
-   <span data-ttu-id="35e69-107">引用 System.Net 命名空间。</span><span class="sxs-lookup"><span data-stu-id="35e69-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="35e69-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="35e69-108">Robust Programming</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="35e69-109">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="35e69-109">.NET Framework Security</span></span>
