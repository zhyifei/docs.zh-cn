---
title: 无法写入输出文件“<filename>”：<error>
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: f29eb628c079f65a520cf5e1ccd8afed549f7cad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787408"
---
# <a name="unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="bed47-102">无法写入输出文件\<文件名 >:\<错误 ></span><span class="sxs-lookup"><span data-stu-id="bed47-102">Unable to write to output file '\<filename>': \<error></span></span>
<span data-ttu-id="bed47-103">创建文件时出现问题。</span><span class="sxs-lookup"><span data-stu-id="bed47-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="bed47-104">无法打开输出文件以进行写入。</span><span class="sxs-lookup"><span data-stu-id="bed47-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="bed47-105">文件（或包含该文件的文件夹）可能由另一个进程打开以供独占使用，或者可能设置了只读特性。</span><span class="sxs-lookup"><span data-stu-id="bed47-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="bed47-106">文件以独占形式打开的常见情形是：</span><span class="sxs-lookup"><span data-stu-id="bed47-106">Common situations where a file is opened exclusively are:</span></span>  
  
- <span data-ttu-id="bed47-107">应用程序已经在运行并使用它的文件。</span><span class="sxs-lookup"><span data-stu-id="bed47-107">The application is already running and using its files.</span></span> <span data-ttu-id="bed47-108">若要解决此问题，请确保应用程序没有运行。</span><span class="sxs-lookup"><span data-stu-id="bed47-108">To solve this problem, make sure that the application is not running.</span></span>  
  
- <span data-ttu-id="bed47-109">其他应用程序已经打开了该文件。</span><span class="sxs-lookup"><span data-stu-id="bed47-109">Another application has opened the file.</span></span> <span data-ttu-id="bed47-110">若要解决此问题，请确保其他应用程序没有访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="bed47-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="bed47-111">是哪个应用程序在访问你的文件并不总是很明显；在这种情况下，重新启动计算机可能是终止该应用程序的最简单的方式。</span><span class="sxs-lookup"><span data-stu-id="bed47-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="bed47-112">即使是项目输出文件中只有一个被标记为只读，也将会引发此异常。</span><span class="sxs-lookup"><span data-stu-id="bed47-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="bed47-113">**错误 ID:** BC31019</span><span class="sxs-lookup"><span data-stu-id="bed47-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bed47-114">更正此错误</span><span class="sxs-lookup"><span data-stu-id="bed47-114">To correct this error</span></span>  
  
1. <span data-ttu-id="bed47-115">再次编译此程序以查看错误是否重复出现。</span><span class="sxs-lookup"><span data-stu-id="bed47-115">Compile the program again to see if the error recurs.</span></span>  
  
2. <span data-ttu-id="bed47-116">如果错误仍然存在，保存所做的工作并重新启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="bed47-116">If the error continues, save your work and restart Visual Studio.</span></span>  
  
3. <span data-ttu-id="bed47-117">如果仍出现错误，请重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="bed47-117">If the error continues, restart the computer.</span></span>  
  
4. <span data-ttu-id="bed47-118">如果错误重复出现，请重新安装 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="bed47-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5. <span data-ttu-id="bed47-119">如果在重新安装之后依然出现错误，请通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="bed47-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="bed47-120">在“文件资源管理器”中检查文件特性</span><span class="sxs-lookup"><span data-stu-id="bed47-120">To check file attributes in File Explorer</span></span>  
  
1. <span data-ttu-id="bed47-121">打开你感兴趣的文件夹。</span><span class="sxs-lookup"><span data-stu-id="bed47-121">Open the folder you are interested in.</span></span>  
  
2. <span data-ttu-id="bed47-122">单击**视图**图标，然后选择**详细信息**。</span><span class="sxs-lookup"><span data-stu-id="bed47-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3. <span data-ttu-id="bed47-123">右键单击列标题，然后选择**属性**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="bed47-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="bed47-124">更改文件或文件夹的特性</span><span class="sxs-lookup"><span data-stu-id="bed47-124">To change the attributes of a file or folder</span></span>  
  
1. <span data-ttu-id="bed47-125">在中**文件资源管理器**，右键单击文件或文件夹，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="bed47-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="bed47-126">在**特性**一部分**常规**选项卡上，清除**只读**框。</span><span class="sxs-lookup"><span data-stu-id="bed47-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3. <span data-ttu-id="bed47-127">按“确定”。</span><span class="sxs-lookup"><span data-stu-id="bed47-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bed47-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="bed47-128">See also</span></span>

- [<span data-ttu-id="bed47-129">与我们交流</span><span class="sxs-lookup"><span data-stu-id="bed47-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
