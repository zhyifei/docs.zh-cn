---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: 6ff9aa23fb6d7dee5c245ed174318f6589e7d245
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624321"
---
# <a name="-bugreport"></a><span data-ttu-id="c5a99-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="c5a99-102">-bugreport</span></span>
<span data-ttu-id="c5a99-103">创建提交 bug 报告时，可以使用一个文件。</span><span class="sxs-lookup"><span data-stu-id="c5a99-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5a99-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5a99-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="c5a99-105">自变量</span><span class="sxs-lookup"><span data-stu-id="c5a99-105">Arguments</span></span>  
  
|<span data-ttu-id="c5a99-106">术语</span><span class="sxs-lookup"><span data-stu-id="c5a99-106">Term</span></span>|<span data-ttu-id="c5a99-107">定义</span><span class="sxs-lookup"><span data-stu-id="c5a99-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="c5a99-108">必需。</span><span class="sxs-lookup"><span data-stu-id="c5a99-108">Required.</span></span> <span data-ttu-id="c5a99-109">将包含 bug 报告文件的名称。</span><span class="sxs-lookup"><span data-stu-id="c5a99-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="c5a99-110">将文件名括在引号 ("") 如果名称包含空格。</span><span class="sxs-lookup"><span data-stu-id="c5a99-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5a99-111">备注</span><span class="sxs-lookup"><span data-stu-id="c5a99-111">Remarks</span></span>  
 <span data-ttu-id="c5a99-112">以下信息添加到`file`:</span><span class="sxs-lookup"><span data-stu-id="c5a99-112">The following information is added to `file`:</span></span>  
  
- <span data-ttu-id="c5a99-113">在编译中的所有源代码文件的副本。</span><span class="sxs-lookup"><span data-stu-id="c5a99-113">A copy of all source-code files in the compilation.</span></span>  
  
- <span data-ttu-id="c5a99-114">编译器选项编译中使用的列表。</span><span class="sxs-lookup"><span data-stu-id="c5a99-114">A list of the compiler options used in the compilation.</span></span>  
  
- <span data-ttu-id="c5a99-115">有关编译器、 公共语言运行时和操作系统的版本信息。</span><span class="sxs-lookup"><span data-stu-id="c5a99-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
- <span data-ttu-id="c5a99-116">编译器输出（如有）。</span><span class="sxs-lookup"><span data-stu-id="c5a99-116">Compiler output, if any.</span></span>  
  
- <span data-ttu-id="c5a99-117">说明问题，这向您发出提示。</span><span class="sxs-lookup"><span data-stu-id="c5a99-117">A description of the problem, for which you are prompted.</span></span>  
  
- <span data-ttu-id="c5a99-118">应修复所预期的问题的说明，这向您发出提示。</span><span class="sxs-lookup"><span data-stu-id="c5a99-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="c5a99-119">因为所有源代码文件的副本包含在`file`，可能想要重现在尽可能短小的程序 （可疑的） 代码缺陷。</span><span class="sxs-lookup"><span data-stu-id="c5a99-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c5a99-120">`-bugreport`选项将生成包含潜在敏感信息的文件。</span><span class="sxs-lookup"><span data-stu-id="c5a99-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="c5a99-121">这包括当前时间，编译器版本[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]版本、 OS 版本、 用户名称、 与其编译器已运行，所有源代码和二进制形式的任何引用的程序集的命令行参数。</span><span class="sxs-lookup"><span data-stu-id="c5a99-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="c5a99-122">可以通过命令行选项指定的服务器端汇集在 Web.config 文件中访问此选项[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5a99-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="c5a99-123">若要防止此情况，修改 Machine.config 文件不允许用户在服务器上进行编译。</span><span class="sxs-lookup"><span data-stu-id="c5a99-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="c5a99-124">如果将此选项用于`-errorreport:prompt`， `-errorreport:queue`，或`-errorreport:send`，和你的应用程序时遇到内部编译器错误中的信息`file`发送到 Microsoft Corporation。</span><span class="sxs-lookup"><span data-stu-id="c5a99-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="c5a99-125">该信息将帮助确定错误的原因的 Microsoft 工程师以及可帮助提高下一版本的 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="c5a99-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="c5a99-126">默认情况下，任何信息不发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="c5a99-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="c5a99-127">但是，当编译应用程序使用`-errorreport:queue`，默认情况下启用，应用程序收集其错误报告。</span><span class="sxs-lookup"><span data-stu-id="c5a99-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="c5a99-128">然后，在计算机的管理员登录，错误报告系统将显示一个弹出窗口，使管理员能够将转发到任何错误报告的 Microsoft 自登录以来发生的。</span><span class="sxs-lookup"><span data-stu-id="c5a99-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5a99-129">`/bugreport`选项不是可从 Visual Studio 开发环境中; 它是可仅在编译时从命令行。</span><span class="sxs-lookup"><span data-stu-id="c5a99-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5a99-130">示例</span><span class="sxs-lookup"><span data-stu-id="c5a99-130">Example</span></span>  
 <span data-ttu-id="c5a99-131">下面的示例将编译`T2.vb`并将错误报告的所有信息都放入该文件`Problem.txt`。</span><span class="sxs-lookup"><span data-stu-id="c5a99-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5a99-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5a99-132">See also</span></span>

- [<span data-ttu-id="c5a99-133">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="c5a99-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="c5a99-134">-调试 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5a99-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="c5a99-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="c5a99-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="c5a99-136">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="c5a99-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="c5a99-137">[（ASP.NET 设置架构） securityPolicy 的 trustLevel 元素](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c5a99-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
