---
title: /bugreport
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0c36cdcaf8d2db0b08e262d6ba8ff2bb774fb233
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="bugreport"></a><span data-ttu-id="fdc3d-102">/bugreport</span><span class="sxs-lookup"><span data-stu-id="fdc3d-102">/bugreport</span></span>
<span data-ttu-id="fdc3d-103">创建文件一个 bug 报告时，可以使用一个文件。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdc3d-104">Syntax</span></span>  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdc3d-105">自变量</span><span class="sxs-lookup"><span data-stu-id="fdc3d-105">Arguments</span></span>  
  
|<span data-ttu-id="fdc3d-106">术语</span><span class="sxs-lookup"><span data-stu-id="fdc3d-106">Term</span></span>|<span data-ttu-id="fdc3d-107">定义</span><span class="sxs-lookup"><span data-stu-id="fdc3d-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="fdc3d-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-108">Required.</span></span> <span data-ttu-id="fdc3d-109">将包含 bug 报告文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="fdc3d-110">将文件名括在双引号 ("") 如果名称包含空格。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdc3d-111">备注</span><span class="sxs-lookup"><span data-stu-id="fdc3d-111">Remarks</span></span>  
 <span data-ttu-id="fdc3d-112">以下信息添加到`file`:</span><span class="sxs-lookup"><span data-stu-id="fdc3d-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="fdc3d-113">编译中所有源代码文件的副本。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="fdc3d-114">用编译中使用的编译器选项的列表。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="fdc3d-115">有关编译器、 公共语言运行时和操作系统的版本信息。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="fdc3d-116">编译器输出（如有）。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="fdc3d-117">此问题，提示你的说明。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="fdc3d-118">应修复您的想法问题的说明，提示你。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="fdc3d-119">因为所有源代码文件的副本包含在`file`，你可能想要重现尽可能短的程序中 （可疑的） 代码缺陷。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fdc3d-120">`/bugreport`选项生成包含潜在敏感信息的文件。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-120">The `/bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="fdc3d-121">这包括当前时间，编译器版本[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]版本、 操作系统版本、 用户名称、 命令行自变量，可编译器已运行，所有源代码和二进制形式的任何引用程序集。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="fdc3d-122">可以通过指定的服务器端编译的 Web.config 文件中的命令行选项来访问此选项[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="fdc3d-123">若要防止此情况，修改要禁止在服务器上进行编译的用户的 Machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="fdc3d-124">如果此选项用于`/errorreport:prompt`， `/errorreport:queue`，或`/errorreport:send`，并且你的应用程序遇到内部编译器错误中的信息`file`发送到 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-124">If this option is used with `/errorreport:prompt`, `/errorreport:queue`, or `/errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="fdc3d-125">该信息将帮助确定错误原因的 Microsoft 工程师以及可帮助改善的下一个版本[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="fdc3d-126">默认情况下，任何信息不发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="fdc3d-127">但是，当你编译应用程序使用`/errorreport:queue`，这默认启用的应用程序收集其错误报告。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-127">However, when you compile an application by using `/errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="fdc3d-128">然后，在计算机的管理员登录，错误报告系统将显示一个弹出窗口，使管理员能够将转发给 Microsoft 自登录以来发生的任何错误报告。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdc3d-129">`/bugreport`选项不是可从 Visual Studio 开发环境中; 它是可用仅编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdc3d-130">示例</span><span class="sxs-lookup"><span data-stu-id="fdc3d-130">Example</span></span>  
 <span data-ttu-id="fdc3d-131">下面的示例将编译`T2.vb`并放置在文件的所有 bug 报告信息`Problem.txt`。</span><span class="sxs-lookup"><span data-stu-id="fdc3d-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdc3d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc3d-132">See Also</span></span>  
 [<span data-ttu-id="fdc3d-133">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="fdc3d-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fdc3d-134">/debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdc3d-134">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="fdc3d-135">/errorreport</span><span class="sxs-lookup"><span data-stu-id="fdc3d-135">/errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)  
 [<span data-ttu-id="fdc3d-136">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="fdc3d-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="fdc3d-137">trustLevel 元素为 securityPolicy （ASP.NET 设置架构）</span><span class="sxs-lookup"><span data-stu-id="fdc3d-137">trustLevel Element for securityPolicy (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/library/729ab04c-03da-4ee5-86b1-be9d08a09369)
