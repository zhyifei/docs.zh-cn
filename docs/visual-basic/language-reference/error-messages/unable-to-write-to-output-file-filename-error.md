---
title: "无法写入输出文件&lt;filename&gt;&quot;:&lt;错误&gt;|Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
dev_langs:
- VB
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0822a732390f308b5f8f1f1431299552fb876e74
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a><span data-ttu-id="80ff1-102">无法写入输出文件&lt;filename&gt;':&lt;错误&gt;</span><span class="sxs-lookup"><span data-stu-id="80ff1-102">Unable to write to output file &#39;&lt;filename&gt;&#39;: &lt;error&gt;</span></span>
<span data-ttu-id="80ff1-103">创建文件时出现问题。</span><span class="sxs-lookup"><span data-stu-id="80ff1-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="80ff1-104">无法打开输出文件以进行写入。</span><span class="sxs-lookup"><span data-stu-id="80ff1-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="80ff1-105">文件（或包含该文件的文件夹）可能由另一个进程打开以供独占使用，或者可能设置了只读特性。</span><span class="sxs-lookup"><span data-stu-id="80ff1-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="80ff1-106">文件以独占形式打开的常见情形是：</span><span class="sxs-lookup"><span data-stu-id="80ff1-106">Common situations where a file is opened exclusively are:</span></span>  
  
-   <span data-ttu-id="80ff1-107">应用程序已经在运行并使用它的文件。</span><span class="sxs-lookup"><span data-stu-id="80ff1-107">The application is already running and using its files.</span></span> <span data-ttu-id="80ff1-108">若要解决此问题，请确保应用程序没有运行。</span><span class="sxs-lookup"><span data-stu-id="80ff1-108">To solve this problem, make sure that the application is not running.</span></span>  
  
-   <span data-ttu-id="80ff1-109">其他应用程序已经打开了该文件。</span><span class="sxs-lookup"><span data-stu-id="80ff1-109">Another application has opened the file.</span></span> <span data-ttu-id="80ff1-110">若要解决此问题，请确保其他应用程序没有访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="80ff1-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="80ff1-111">是哪个应用程序在访问你的文件并不总是很明显；在这种情况下，重新启动计算机可能是终止该应用程序的最简单的方式。</span><span class="sxs-lookup"><span data-stu-id="80ff1-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="80ff1-112">即使是项目输出文件中只有一个被标记为只读，也将会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="80ff1-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="80ff1-113">**错误 ID:** BC31019</span><span class="sxs-lookup"><span data-stu-id="80ff1-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80ff1-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="80ff1-114">To correct this error</span></span>  
  
1.  <span data-ttu-id="80ff1-115">再次编译此程序以查看错误是否重复出现。</span><span class="sxs-lookup"><span data-stu-id="80ff1-115">Compile the program again to see if the error recurs.</span></span>  
  
2.  <span data-ttu-id="80ff1-116">如果仍出现错误，请保存你的工作并重新启动 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80ff1-116">If the error continues, save your work and restart [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span></span>  
  
3.  <span data-ttu-id="80ff1-117">如果仍出现错误，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="80ff1-117">If the error continues, restart the computer.</span></span>  
  
4.  <span data-ttu-id="80ff1-118">如果错误重复出现，请重新安装 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="80ff1-118">If the error recurs, reinstall [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
5.  <span data-ttu-id="80ff1-119">如果在重新安装之后依然出现错误，请通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="80ff1-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="80ff1-120">在“文件资源管理器”中检查文件特性</span><span class="sxs-lookup"><span data-stu-id="80ff1-120">To check file attributes in File Explorer</span></span>  
  
1.  <span data-ttu-id="80ff1-121">打开你感兴趣的文件夹。</span><span class="sxs-lookup"><span data-stu-id="80ff1-121">Open the folder you are interested in.</span></span>  
  
2.  <span data-ttu-id="80ff1-122">单击**视图**图标，然后选择**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="80ff1-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3.  <span data-ttu-id="80ff1-123">右键单击列标题，然后选择**属性**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="80ff1-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="80ff1-124">更改文件或文件夹的特性</span><span class="sxs-lookup"><span data-stu-id="80ff1-124">To change the attributes of a file or folder</span></span>  
  
1.  <span data-ttu-id="80ff1-125">在**文件资源管理器**，用鼠标右键单击文件或文件夹，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="80ff1-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="80ff1-126">在**属性**部分**常规**选项卡上，清除**只读**框。</span><span class="sxs-lookup"><span data-stu-id="80ff1-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3.  <span data-ttu-id="80ff1-127">Press **OK**.</span><span class="sxs-lookup"><span data-stu-id="80ff1-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80ff1-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80ff1-128">See Also</span></span>  
 [<span data-ttu-id="80ff1-129">与我们交流</span><span class="sxs-lookup"><span data-stu-id="80ff1-129">Talk to Us</span></span>](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
