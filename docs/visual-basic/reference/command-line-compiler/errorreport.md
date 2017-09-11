---
title: "/errorreport |Microsoft 文档"
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2f9a9daf6aed6348baeb2c4de2fe5caef70f52b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="errorreport"></a><span data-ttu-id="183e6-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="183e6-102">/errorreport</span></span>
<span data-ttu-id="183e6-103">指定 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 编译器应报告内部编译器错误的方式。</span><span class="sxs-lookup"><span data-stu-id="183e6-103">Specifies how the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="183e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="183e6-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="183e6-105">备注</span><span class="sxs-lookup"><span data-stu-id="183e6-105">Remarks</span></span>  
 <span data-ttu-id="183e6-106">此选项可以方便地向报表[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]到内部编译器错误 (ICE) [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="183e6-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team at Microsoft.</span></span> <span data-ttu-id="183e6-107">默认情况下，编译器会向 Microsoft 发送任何信息。</span><span class="sxs-lookup"><span data-stu-id="183e6-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="183e6-108">但是，如果您遇到内部编译器错误，此选项允许您向 Microsoft 报告错误。</span><span class="sxs-lookup"><span data-stu-id="183e6-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="183e6-109">该信息将帮助确定的原因的 Microsoft 工程师以及可帮助改善的下一个版本[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="183e6-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="183e6-110">发送报告用户的能力取决于计算机和用户策略权限。</span><span class="sxs-lookup"><span data-stu-id="183e6-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="183e6-111">下表总结了的效果`/errorreport`选项。</span><span class="sxs-lookup"><span data-stu-id="183e6-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="183e6-112">选项</span><span class="sxs-lookup"><span data-stu-id="183e6-112">Option</span></span>|<span data-ttu-id="183e6-113">行为</span><span class="sxs-lookup"><span data-stu-id="183e6-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="183e6-114">如果内部编译器错误发生，弹出对话框，以便您可以查看编译器收集的确切数据。</span><span class="sxs-lookup"><span data-stu-id="183e6-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="183e6-115">可以确定是否存在任何错误报告中的敏感信息并决定是否将其发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="183e6-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="183e6-116">如果你决定发送它，并且计算机和用户策略设置允许这样，编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="183e6-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="183e6-117">排入队列的错误报告。</span><span class="sxs-lookup"><span data-stu-id="183e6-117">Queues the error report.</span></span> <span data-ttu-id="183e6-118">当使用管理员权限登录时，可以报告自上次登录以来的任何失败 （将不会提示您发送失败报告一次以上每隔三天）。</span><span class="sxs-lookup"><span data-stu-id="183e6-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="183e6-119">这是默认行为时`/errorreport`未指定选项。</span><span class="sxs-lookup"><span data-stu-id="183e6-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="183e6-120">如果发生内部编译器错误，并且计算机和用户策略设置允许这样，编译器会将数据发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="183e6-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="183e6-121">该选项`/errorReport:send`尝试自动向 Microsoft 发送错误的信息。</span><span class="sxs-lookup"><span data-stu-id="183e6-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="183e6-122">此选项取决于注册表。</span><span class="sxs-lookup"><span data-stu-id="183e6-122">This option depends on the registry.</span></span> <span data-ttu-id="183e6-123">有关在注册表中设置适当的值的详细信息，请参阅[如何自动发送错误报告，在 Visual Studio 2008 命令行工具中打开](http://go.microsoft.com/fwlink/?LinkID=184695)。</span><span class="sxs-lookup"><span data-stu-id="183e6-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="183e6-124">如果发生内部编译器错误，它不会收集或发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="183e6-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="183e6-125">编译器将发送一个错误，它通常包含某些源代码次包括堆栈的数据。</span><span class="sxs-lookup"><span data-stu-id="183e6-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="183e6-126">如果`/errorreport`与使用[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，则发送整个源文件。</span><span class="sxs-lookup"><span data-stu-id="183e6-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="183e6-127">此选项适用于[/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)选项，因为它允许 Microsoft 工程师能更轻松地重现错误。</span><span class="sxs-lookup"><span data-stu-id="183e6-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="183e6-128">`/errorreport`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="183e6-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="183e6-129">示例</span><span class="sxs-lookup"><span data-stu-id="183e6-129">Example</span></span>  
 <span data-ttu-id="183e6-130">下面的代码试图编译`T2.vb`，如果编译器遇到内部编译器错误，它会提示你向 Microsoft 发送错误报告。</span><span class="sxs-lookup"><span data-stu-id="183e6-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="183e6-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="183e6-131">See Also</span></span>  
 <span data-ttu-id="183e6-132">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="183e6-132">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="183e6-133"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="183e6-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="183e6-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span><span class="sxs-lookup"><span data-stu-id="183e6-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span></span>
