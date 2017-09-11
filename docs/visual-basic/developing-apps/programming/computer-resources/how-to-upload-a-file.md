---
title: "如何：在 Visual Basic 中上传文件"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- networks, uploading files
- files, uploading
- uploading files
- UploadFile method
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 29baf1f420cece6e0b05f9638b30a326178a013d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-upload-a-file-in-visual-basic"></a><span data-ttu-id="4b0cc-102">如何：在 Visual Basic 中上传文件</span><span class="sxs-lookup"><span data-stu-id="4b0cc-102">How to: Upload a File in Visual Basic</span></span>
<span data-ttu-id="4b0cc-103">可使用 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> 方法上传文件并将文件存储到远程位置。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-103">The <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> method can be used to upload a file and store it to a remote location.</span></span> <span data-ttu-id="4b0cc-104">如果 `ShowUI` 参数设置为 `True`，则显示一个对话框，该对话框显示上传进度并允许用户取消该操作。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-104">If the `ShowUI` parameter is set to `True`, a dialog box is displayed that shows the progress of the upload and allows users to cancel the operation.</span></span>  
  
### <a name="to-upload-a-file"></a><span data-ttu-id="4b0cc-105">上传文件</span><span class="sxs-lookup"><span data-stu-id="4b0cc-105">To upload a file</span></span>  
  
-   <span data-ttu-id="4b0cc-106">可以使用 `UploadFile` 方法上传文件，同时将源文件的位置和目标目录位置指定为字符串或 URI（统一资源标识符）。此示例将文件 `Order.txt` 上传到 `http://www.cohowinery.com/uploads.aspx`。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-106">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI (Uniform Resource Identifier).This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`.</span></span>  
  
     <span data-ttu-id="4b0cc-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4b0cc-107">[!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]</span></span>  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a><span data-ttu-id="4b0cc-108">上传文件并显示操作进度</span><span class="sxs-lookup"><span data-stu-id="4b0cc-108">To upload a file and show the progress of the operation</span></span>  
  
-   <span data-ttu-id="4b0cc-109">可以使用 `UploadFile` 方法上传文件，同时将源文件的位置和目标目录位置指定为字符串或 URI。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-109">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI.</span></span> <span data-ttu-id="4b0cc-110">此示例在不提供用户名或密码的情况下将文件 `Order.txt` 上传到 `http://www.cohowinery.com/uploads.aspx`显示了上传操作的进度，并将将超时间隔为 500 毫秒。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-110">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx` without supplying a user name or password, shows the progress of the upload, and has a time-out interval of 500 milliseconds.</span></span>  
  
     <span data-ttu-id="4b0cc-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4b0cc-111">[!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]</span></span>  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a><span data-ttu-id="4b0cc-112">上传文件并提供用户名和密码</span><span class="sxs-lookup"><span data-stu-id="4b0cc-112">To upload a file, supplying a user name and password</span></span>  
  
-   <span data-ttu-id="4b0cc-113">可以使用 `UploadFile` 方法上传文件，同时将源文件的位置和目标目录位置指定为字符串或 URI，并指定用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-113">Use the `UploadFile` method to upload a file, specifying the source file's location and the target directory location as a string or URI, and specifying the user name and the password.</span></span> <span data-ttu-id="4b0cc-114">此示例将文件 `Order.txt` 上传到 `http://www.cohowinery.com/uploads.aspx`，并提供了用户名 `anonymous` 和空白密码。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-114">This example uploads the file `Order.txt` to `http://www.cohowinery.com/uploads.aspx`, supplying the user name `anonymous` and a blank password.</span></span>  
  
     <span data-ttu-id="4b0cc-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4b0cc-115">[!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4b0cc-116">可靠编程</span><span class="sxs-lookup"><span data-stu-id="4b0cc-116">Robust Programming</span></span>  
 <span data-ttu-id="4b0cc-117">以下情况可能会引发异常：</span><span class="sxs-lookup"><span data-stu-id="4b0cc-117">The following conditions may throw an exception:</span></span>  
  
-   <span data-ttu-id="4b0cc-118">本地文件路径无效 (<xref:System.ArgumentException>)。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-118">The local file path is not valid (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="4b0cc-119">身份验证失败 (<xref:System.Security.SecurityException>)。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-119">Authentication failed (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="4b0cc-120">连接超时 (<xref:System.TimeoutException>)。</span><span class="sxs-lookup"><span data-stu-id="4b0cc-120">The connection timed out (<xref:System.TimeoutException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0cc-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b0cc-121">See Also</span></span>  
 <span data-ttu-id="4b0cc-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4b0cc-122"><xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName></span></span>   
 <span data-ttu-id="4b0cc-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span><span class="sxs-lookup"><span data-stu-id="4b0cc-123"><xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A></span></span>   
 <span data-ttu-id="4b0cc-124">[如何：下载文件](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span><span class="sxs-lookup"><span data-stu-id="4b0cc-124">[How to: Download a File](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md) </span></span>  
 [<span data-ttu-id="4b0cc-125">如何：分析文件路径</span><span class="sxs-lookup"><span data-stu-id="4b0cc-125">How to: Parse File Paths</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

